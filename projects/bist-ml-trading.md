---
layout: single
title: "Disclosure-Driven ML Trading on Borsa İstanbul"
permalink: /projects/bist-ml-trading/
author_profile: true
classes: wide
---

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
<strong>Key Contribution:</strong> This project focuses on the <em>engineering and evaluation challenges</em> of transforming public disclosure data into tradable signals. The hard parts aren't the models—they're the data alignment, leakage prevention, and realistic performance assessment.
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

<style>
  @import url('/assets/css/custom.css');
</style>
