---
layout: single
title: "Disclosure-Driven ML Trading on Borsa İstanbul"
permalink: /projects/bist-ml-trading/
author_profile: true
classes: wide
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Manrope:wght@300;400;600;700&display=swap');

:root {
  --primary-dark: #1a1a2e;
  --primary-blue: #0f3460;
  --accent-teal: #16a085;
  --accent-coral: #e94560;
  --bg-color: #ffffff;
  --card-bg: #ffffff;
  --text-dark: #2c3e50;
  --border-color: rgba(0,0,0,0.06);
  --shadow-color: rgba(0,0,0,0.07);
}

body.dark-mode {
  --primary-dark: #ecf0f1;
  --text-dark: #ecf0f1;
  --bg-color: #1a1a2e;
  --card-bg: #252541;
  --border-color: rgba(255,255,255,0.1);
  --shadow-color: rgba(0,0,0,0.3);
}

/* Hide duplicate author name */
.sidebar .author__name {
  display: none !important;
}

body {
  background-color: var(--bg-color);
  font-family: 'Manrope', -apple-system, BlinkMacSystemFont, sans-serif;
  font-size: 16px;
}

h1, h2, h3, h4 {
  font-family: 'Space Mono', monospace;
  font-weight: 700;
  color: var(--text-dark);
}

.project-header-banner {
  background: linear-gradient(135deg, #0f3460 0%, #1a1a2e 100%);
  margin: -2rem -2rem 2rem;
  padding: 2.5rem 2rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.project-header-banner::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 30% 20%, rgba(22, 160, 133, 0.15) 0%, transparent 50%),
    radial-gradient(circle at 70% 80%, rgba(233, 69, 96, 0.15) 0%, transparent 50%);
  pointer-events: none;
}

.project-header-banner h1 {
  color: white;
  font-size: 1.75rem;
  margin-bottom: 0.65rem;
  position: relative;
  z-index: 1;
  line-height: 1.3;
}

.project-subtitle {
  color: rgba(255,255,255,0.9);
  font-size: 0.95rem;
  font-weight: 300;
  font-style: italic;
  position: relative;
  z-index: 1;
}

.project-detail-page {
  max-width: 850px;
  margin: 0 auto;
  padding: 0 1.5rem 2rem;
}

.project-detail-page h2 {
  font-size: 1.4rem;
  color: var(--text-dark);
  margin-top: 2.25rem;
  margin-bottom: 0.9rem;
  padding-bottom: 0.45rem;
  border-bottom: 3px solid var(--accent-teal);
}

.project-detail-page h3 {
  font-size: 1.1rem;
  color: var(--primary-blue);
  margin-top: 1.5rem;
  margin-bottom: 0.65rem;
}

.project-detail-page p {
  font-size: 0.9rem;
  line-height: 1.6;
  color: var(--text-dark);
  margin-bottom: 0.85rem;
}

.project-detail-page li {
  font-size: 0.9rem;
  line-height: 1.6;
  color: var(--text-dark);
  margin-bottom: 0.45rem;
}

.project-detail-page ul {
  list-style: none;
  padding-left: 0;
  margin-bottom: 1rem;
  margin-top: 0.5rem;
}

.project-detail-page ul li {
  padding-left: 1.4rem;
  position: relative;
}

.project-detail-page ul li::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: var(--accent-teal);
  font-weight: bold;
  font-size: 1.1em;
}

.highlight-box {
  background: linear-gradient(135deg, rgba(22, 160, 133, 0.08), rgba(15, 52, 96, 0.05));
  border-left: 4px solid var(--accent-teal);
  padding: 1.15rem 1.4rem;
  margin: 1.5rem 0;
  border-radius: 0 6px 6px 0;
}

.highlight-box p {
  margin-bottom: 0;
  font-size: 0.9rem;
}

.highlight-box strong {
  color: var(--accent-teal);
  font-weight: 600;
}

pre {
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  padding: 1rem;
  border-radius: 6px;
  overflow-x: auto;
  line-height: 1.4;
  font-size: 0.8rem;
  margin: 1rem 0;
}

code {
  font-family: 'Space Mono', monospace;
  font-size: 0.85em;
  background: rgba(22, 160, 133, 0.08);
  padding: 0.15em 0.35em;
  border-radius: 3px;
  color: var(--accent-teal);
}

pre code {
  background: none;
  padding: 0;
  color: var(--text-dark);
}

hr {
  border: none;
  border-top: 1px solid var(--border-color);
  margin: 1.75rem 0;
}

.page__content {
  color: var(--text-dark);
}

.sidebar {
  background: var(--card-bg);
}

@media (max-width: 768px) {
  .project-header-banner {
    margin: -1rem -1rem 1.5rem;
    padding: 2rem 1.5rem;
  }
  
  .project-header-banner h1 {
    font-size: 1.5rem;
  }
  
  .project-subtitle {
    font-size: 0.85rem;
  }
  
  .project-detail-page h2 {
    font-size: 1.25rem;
  }
}
</style>

<div class="project-header-banner">
  <h1>Disclosure-Driven ML Trading on Borsa İstanbul</h1>
  <p class="project-subtitle">Event-aware feature engineering, leakage-safe labels, and realistic backtests</p>
</div>

<div class="project-detail-page">

## Overview

This project investigates whether public company disclosures contain predictive information for short-horizon stock returns on Borsa İstanbul (BIST). I built an end-to-end, leakage-aware machine learning pipeline that:

- Aligns disclosures to tradable timestamps using exchange-aware calendars
- Engineers price-based and event-based features with strict temporal discipline
- Constructs forward-looking labels across multiple horizons (D1/D5/D20)
- Evaluates models using both ML metrics and portfolio backtests with realistic transaction costs

The goal isn't just prediction accuracy—it's building a system that could actually be deployed in a trading environment.

---

<div class="highlight-box">
<p><strong>Key Contribution:</strong> This project focuses on the <em>engineering and evaluation challenges</em> of transforming public disclosure data into tradable signals. The hard parts aren't the models—they're the data alignment, leakage prevention, and realistic performance assessment.</p>
</div>

---

## Motivation

Public disclosures are one of the few **legally exploitable information sources** in equity markets. Unlike insider information or material non-public data, disclosure-based signals are available to all market participants simultaneously.

However, transforming disclosures into tradable signals is non-trivial:

- **Timing matters:** When can you actually trade after a disclosure?
- **Market microstructure:** Holidays, early closes, trading halts
- **Data leakage:** It's surprisingly easy to accidentally use future information
- **Evaluation realism:** Backtest performance often doesn't survive real trading

This project addresses these challenges systematically.

---

## Data Sources & Scope

### Primary Data

- **Public company disclosures** published via KAP (Public Disclosure Platform)
- **Daily OHLCV statistics** from Borsa İstanbul
- **BIST equity universe** with sufficient trading history and liquidity

### Data Attribution Note

Raw data ingestion from KAP and BIST is **not my original contribution**. My work begins after raw data is available and focuses on:

- Data cleaning and quality validation
- Timestamp alignment and calendar management
- Feature engineering and label construction
- Model training and evaluation
- Backtesting framework development

---

## Core Technical Challenges

### 1. Disclosure Timing & Tradability

Disclosures arrive at various times:

- During trading hours (immediate impact)
- After market close (next-day tradability)
- On weekends or holidays (delayed tradability)
- During trading halts (complex handling)

**Solution:** Every disclosure is anchored to the **first tradable timestamp** using an exchange-aware calendar that accounts for:

- Regular trading days and hours
- National holidays and religious observances
- Early market closes and half-days
- Stock-specific trading halts

This ensures that features and labels reflect what was **actually knowable and actionable** at decision time.

### 2. Data Leakage Prevention

Financial ML is notorious for leakage—using information that wouldn't have been available when making the prediction. Common mistakes include:

- Computing technical indicators with look-ahead bias
- Using same-day closing prices for next-day predictions
- Cross-sectional statistics that include future data
- Label leakage through feature engineering

**Solution:** Implemented multiple safeguards:

- All price-based features are **strictly lagged**
- Cross-sectional statistics computed using **only prior-day information**
- Automated diagnostics to flag potential leakage
- Manual inspection of feature computation logic
- Time-series cross-validation with mandatory gap days

### 3. Realistic Label Construction

Labels must represent **tradable forward returns** from decision time T to horizon T+H, accounting for:

- Trading-day counting (not calendar days)
- Transaction costs and slippage assumptions
- Stock-specific liquidity constraints

**Implementation:**

- **D1 labels:** Next trading day returns
- **D5 labels:** Five trading days forward
- **D20 labels:** Twenty trading days forward

Multiple label types supported:

- Binary classification (above/below threshold)
- Regression targets (raw returns)
- Ranking consensus (for portfolio construction)

---

## Pipeline Architecture

```
1. Data Ingestion
   ├── Clean OHLCV statistics (handle corporate actions, splits)
   └── Clean disclosure metadata (normalize text, extract timestamps)

2. Temporal Alignment
   ├── Map disclosures to trading calendar
   ├── Identify first tradable timestamp
   └── Create event windows for feature engineering

3. Feature Engineering
   ├── Technical indicators (RSI, moving averages, volatility)
   ├── Volume & liquidity metrics
   ├── Momentum & mean-reversion signals
   ├── Cross-sectional rankings (z-scores, percentiles)
   └── Event-based features (disclosure counts, recency, timing)

4. Label Construction
   ├── Forward returns across horizons (D1/D5/D20)
   ├── Trading-day aware calculations
   └── Multiple label types (binary, regression, ranking)

5. Model Training
   ├── LightGBM gradient boosted trees
   ├── Time-series cross-validation
   ├── Hyperparameter tuning
   └── Threshold optimization for portfolio construction

6. Evaluation
   ├── ML metrics (ROC-AUC, Precision-Recall, IC)
   ├── Probability calibration assessment
   └── Portfolio backtests with transaction costs
```

---

## Feature Engineering

Features are organized into groups, all designed to be **observable at decision time**:

### Technical Indicators

- RSI (Relative Strength Index)
- Moving averages (5/10/20-day)
- Bollinger Bands and volatility measures
- Price gaps and momentum

### Volume & Liquidity

- Average daily volume (ADV)
- Dollar volume and turnover
- Volume-weighted metrics
- Money flow indicators

### Momentum & Mean Reversion

- Short-term returns (1/3/5-day)
- Long-term trends (20/60-day)
- Distance from moving averages
- Reversal signals

### Cross-Sectional Features

- Percentile ranks within universe
- Z-scores relative to peer group
- Sector-relative metrics

### Event-Based Features

- Disclosure counts (recent windows)
- Time since last disclosure
- After-hours disclosure flags
- Disclosure type indicators

All features undergo **strict temporal validation** to ensure no look-ahead bias.

---

## Modeling Approach

### Algorithm Choice

**LightGBM** gradient boosted decision trees for:

- Strong performance on tabular data
- Native handling of missing values
- Fast training on medium-sized datasets
- Built-in feature importance

### Training Framework

- **Time-series cross-validation** with expanding window
- **Gap days** between training and validation (prevents leakage)
- **Walk-forward validation** to simulate production deployment
- Decision threshold tuning using portfolio-level metrics (not just accuracy)

### Hyperparameter Optimization

Focus on parameters that matter for generalization:

- Tree depth and number of leaves
- Learning rate and number of boosting rounds
- Feature subsampling ratios
- Regularization terms

---

## Evaluation Framework

Models are evaluated at multiple levels:

### ML Performance Metrics

- **ROC-AUC:** Ranking quality across all thresholds
- **Precision-Recall:** Performance at actionable decision points
- **Information Coefficient (IC):** Rank correlation between predictions and outcomes
- **Calibration curves:** Are predicted probabilities well-calibrated?

### Portfolio Backtests

The ultimate test: **Can this actually make money?**

**Strategy:**

- Long-only daily rebalancing
- Top-N stocks by predicted return
- Equal-weight or score-weighted allocation

**Realistic Assumptions:**

- Transaction costs (bid-ask spread + commission)
- No intraday execution modeling (conservative)
- No leverage or shorting (simple baseline)

**Metrics:**

- Sharpe ratio and risk-adjusted returns
- Maximum drawdown
- Win rate and profit factor
- Turnover and capacity constraints

---

## Results & Insights

*This section would contain specific findings from your analysis. Since these are specific to your data and results, I'm leaving this for you to fill in. Consider including:*

- Model performance across different horizons
- Which features are most predictive
- Performance across different market regimes
- Transaction cost sensitivity analysis
- Comparison to simple baselines

---

## Limitations & Future Work

### Current Limitations

- **No intraday execution:** All trades assumed at daily close prices
- **Limited text features:** Disclosure semantics underutilized
- **Static universe:** No dynamic stock selection based on liquidity
- **Regime-agnostic:** Single model for all market conditions

### Potential Extensions

**NLP Enhancement**

- Sentiment analysis of disclosure text
- Topic modeling and event classification
- Named entity recognition for key information

**Model Improvements**

- Regime-aware models (bull/bear/sideways)
- Sector-specific or conditional models
- Ensemble approaches combining multiple signals

**Execution Realism**

- Intraday execution modeling
- Market impact estimation
- Liquidity-aware position sizing
- Optimal execution algorithms

**Robustness Testing**

- Stress testing across crisis periods
- Sensitivity to feature engineering choices
- Out-of-sample validation on new time periods

---

## Technical Stack

**Languages:** Python  
**ML Libraries:** LightGBM, scikit-learn, pandas, numpy  
**Backtesting:** Custom framework with vectorized operations  
**Validation:** Time-series cross-validation with strict temporal controls

---

## Key Takeaways

1. **Leakage prevention is harder than it looks:** Requires constant vigilance and systematic validation
2. **Realistic evaluation matters:** ML metrics don't guarantee trading profitability
3. **Feature engineering > model selection:** Time spent on thoughtful features beats hyperparameter tuning
4. **Production constraints are first-class concerns:** Build evaluation that reflects real deployment from day one

---

## References & Resources

- [Borsa İstanbul Market Structure](https://www.borsaistanbul.com/)
- [KAP Public Disclosure Platform](https://www.kap.org.tr/)
- *Advances in Financial Machine Learning* by Marcos López de Prado
- Standard quantitative finance evaluation frameworks

</div>
