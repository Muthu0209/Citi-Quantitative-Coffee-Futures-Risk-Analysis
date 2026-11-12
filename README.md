# Citi-Quantitative-Coffee-Futures-Risk-Analysis
Quantitative pricing and risk management analysis for coffee futures, completed as part of Citi's Markets Quantitative Analysis job simulation (via Forage). Applied Cost of Carry, Black-Scholes, Monte Carlo simulation, and digital options pricing models, plus risk management strategies for market, credit, and operational risk.


The project covers the full workflow of a markets quant: pricing a commodity future, valuing options on it, simulating price paths, structuring a product for a client, and recommending risk controls.

---

## Contents

| # | Deliverable | Models and methods | File |
|---|-------------|--------------------|------|
| 2 | **Fair Price Analysis: Coffee Futures** | Cost of Carry, Black-Scholes, Monte Carlo (GBM) | `Coffee_Futures_Analysis.docx` |
| 3 | **Structured Securities Proposal** | Digital (binary) options, Monte Carlo scenarios, risk mitigation | `Structured_Securities_Proposal.docx` |
| 4 | **Risk Management Analysis** | Market, credit and operational risk strategies | `Risk_Management_Analysis.docx` |

The completion certificate is also included in the repo.

---

## 1. Fair Price Analysis

**Inputs:** spot S = $1.20/lb, risk-free rate r = 2%, storage cost d = 1%, maturity T = 0.5 years, strike X = $1.25, volatility σ = 25%.

| Model | Formula | Result |
|-------|---------|--------|
| Cost of Carry (futures) | `F = S · e^((r + d)T)` | **$1.218 / lb** |
| Black-Scholes (call option) | `C = S·N(d1) − X·e^(−rT)·N(d2)` | **$0.068** (out-of-the-money) |
| Monte Carlo (10,000 GBM paths, 252 steps) | Simulated terminal price | Mean **$1.210**, 5th pct **$0.892**, 95th pct **$1.592** |

**Takeaway:** the simulated mean ($1.210) is consistent with the Cost of Carry fair price ($1.218). The wide 5th–95th percentile band shows how much weather, supply, demand and geopolitical risk matter in coffee markets, and why hedging is needed.

The analysis also discusses how supply shocks, demand shifts, geopolitics and macro indicators (interest rates, inflation) move the fair price.

---

## 2. Structured Securities Proposal

**Client scenario:** a high-risk investor who wants to profit from large coffee price moves.
**Recommended product:** digital options on coffee futures.

| Instrument | Pricing formula | Value (per $1 payoff) |
|------------|-----------------|-----------------------|
| Digital Call | `e^(−rT) · N(d2)` | **$0.392** |
| Digital Put | `e^(−rT) · N(−d2)` | **$0.598** |

Monte Carlo scenario estimates: about 39.6% probability that price ends above the $1.25 strike (bull) and about 60.4% below it (bear).

**Recommendation:** a digital call for upside exposure, a digital put as the higher-probability payoff, or a **digital strangle** (both) to profit from large moves in either direction.

**Risk mitigation:** diversification, position sizing, GARCH-based volatility monitoring, Monte Carlo stress testing and stop-loss rules.

---

## 3. Risk Management Analysis

| Scenario | Risk type | Strategies |
|----------|-----------|------------|
| Poor weather expected to raise coffee prices | **Market risk** | Buy call options (Black-Scholes), long futures (Cost of Carry), VaR-informed position sizing |
| New supplier in a volatile economy | **Credit risk** | Altman Z-Score, Credit Default Swap, collateral based on Potential Future Exposure |
| Rising manual trading errors | **Operational risk** | Process automation, audits and compliance checks, IT infrastructure and staff training |

---

## Tools and Concepts

- **Python:** NumPy, SciPy, for the pricing and simulation work
- **Pricing models:** Cost of Carry, Black-Scholes, digital option pricing
- **Simulation:** Monte Carlo with Geometric Brownian Motion
- **Risk metrics:** Value at Risk (VaR), Altman Z-Score, Potential Future Exposure, GARCH volatility

---

## Repository Structure

```
.
├── README.md
├── Citi - Markets Quantitative Analysis (MQA) Job Simulation.pdf   # Certificate of completion
├── Coffee_Futures_Analysis.docx
├── Structured_Securities_Proposal.docx
└── Risk_Management_Analysis.docx
```

---

## Certificate

Completed the Citi Markets Quantitative Analysis job simulation on Forage in March 2026, covering financial math fundamentals, commodity pricing (coffee), hedging and structuring securities, and managing risk across market trade units.

---

## Disclaimer

This is an educational job simulation. All market data is illustrative, and nothing here is investment advice.

## Author

**Muthulakshmi Viswanathan**
GitHub: [@Muthu0209](https://github.com/Muthu0209)
