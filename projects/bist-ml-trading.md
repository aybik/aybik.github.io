---
layout: default
title: "Disclosure-Driven ML Trading on Borsa İstanbul"
permalink: /projects/bist-ml-trading/
---

# Disclosure-Driven ML Trading on Borsa İstanbul

_Event-aware feature engineering, leakage-safe labels, and realistic backtests_

---

This project studies whether public company disclosures contain predictive
information for short-horizon stock returns on Borsa İstanbul (BIST).

I build an end-to-end, leakage-aware machine learning pipeline that aligns
disclosures to tradable timestamps, engineers price- and event-based features,
constructs forward-looking labels (D1/D5/D20), and evaluates models using both
ML metrics and portfolio backtests.

---

## Motivation

Public disclosures are one of the few legally exploitable information sources
in equity markets. However, transforming disclosures into tradable signals is
non-trivial due to timing, market microstructure, and data leakage risks.

This project focuses on the engineering and evaluation challenges involved in
using disclosure data within a realistic trading framework.

---

## Data Sources & Attribution

- Public company disclosures published via KAP
- Daily price and volume statistics from Borsa İstanbul
- BIST equity universe with sufficient trading history

**Data collection note:**
Raw data ingestion from KAP and BIST is not my original contribution.
My work begins after raw data is available and focuses on cleaning, alignment,
feature engineering, labeling, modeling, and evaluation.

---

## Core Challenges

### Disclosure timing & tradability
Disclosures may arrive during trading hours, after market close, or on
non-trading days. Each disclosure is anchored to the first tradable timestamp
using an exchange-aware calendar that accounts for holidays, half-days, and
early closes.

### Leakage prevention
All price-based features are strictly lagged. Cross-sectional statistics are
computed using only prior-day information, and automated diagnostics flag
potential leakage.

### Realistic labels
Labels represent tradable forward returns from decision time T to T+H across
multiple trading-aware horizons.

---

## Pipeline Overview

1. Clean daily OHLCV statistics
2. Clean and normalize disclosure metadata
3. Align disclosures to trading days and horizons
4. Engineer technical, volume, momentum, and event-based features
5. Build leakage-safe forward-looking labels (D1/D5/D20)
6. Train ML models with time-series cross-validation
7. Evaluate predictions and backtest portfolios

---

## Feature Engineering

Feature groups include:

- Technical indicators (RSI, moving averages, volatility, gaps)
- Volume and liquidity metrics (ADV, dollar volume, money flow)
- Momentum and mean-reversion signals
- Cross-sectional ranks and z-scores
- Disclosure-based event features (counts, recency, after-hours flags)

All features are designed to be observable at decision time.

---

## Labeling & Horizons

Labels are constructed as forward-looking returns over trading-aware horizons:

- **D1** – next trading day
- **D5** – five trading days
- **D20** – twenty trading days

Binary, thresholded, regression, and consensus labels are supported, enabling
both classification- and ranking-based evaluation.

---

## Modeling & Training

- Gradient-boosted decision trees (LightGBM)
- Time-series cross-validation with gap days
- Decision thresholds tuned using portfolio-level metrics

---

## Evaluation & Backtesting

Models are evaluated using:

- ROC-AUC and Precision–Recall
- Probability calibration
- Information Coefficient (IC)
- Long-only daily portfolio backtests with transaction costs

---

## Limitations

- No intraday execution modeling
- Limited use of disclosure text semantics
- Performance varies across stocks and market regimes

---

## Future Work

- NLP embeddings for disclosure text
- Regime-aware or sector-conditional models
- More realistic transaction cost and liquidity modeling

---

## References

- Borsa İstanbul market structure documentation
- KAP public disclosure framework
- Standard quantitative finance evaluation metrics
