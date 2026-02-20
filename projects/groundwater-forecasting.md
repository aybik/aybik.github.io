---
layout: single
title: "Groundwater Level Forecasting System"
permalink: /projects/groundwater-forecasting/
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

.sidebar .author__name {
  display: none !important;
}

.page__title {
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
  margin: -0.5rem 0 2rem;
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

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1rem;
  margin: 1.5rem 0;
}

.stat-box {
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 1.25rem;
  text-align: center;
}

.stat-value {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--accent-teal);
  font-family: 'Space Mono', monospace;
  margin-bottom: 0.25rem;
}

.stat-label {
  font-size: 0.85rem;
  color: var(--text-dark);
  opacity: 0.8;
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

  .stats-grid {
    grid-template-columns: 1fr 1fr;
  }
}
</style>

<div class="project-header-banner">
  <h1>Groundwater Level Forecasting System</h1>
  <p class="project-subtitle">Production-ready multi-horizon forecasting pipeline for water resource monitoring</p>
</div>

<div class="project-detail-page" markdown="1">

## Overview

I developed a production-ready machine learning system to forecast groundwater levels at 7, 14, 21, and 28-day horizons using daily well monitoring data.

This project was delivered as an **Upwork client project**, with a strong focus on deployability, uncertainty-aware outputs, and operational monitoring.

---

## Problem

Groundwater managers need short-term forecasts to plan pumping and risk mitigation, but historical data is limited and behavior shifts across seasons.

This created key challenges:

- High volatility in depletion periods
- Limited training history (~448 daily samples)
- Risk of overfitting with complex models
- Need for interpretable, deployable predictions

### Constraints

- Strict time-series validation (no random split leakage)
- Forecasts must use only historically available features
- Outputs need confidence and alert-level interpretation

---

<div class="highlight-box">
<p><strong>Solution:</strong> A complete forecasting workflow using 44 engineered features, robust horizon-specific Huber models, prediction intervals, and production monitoring with alert logic and retraining triggers.</p>
</div>

---

## Technical Stack

- **Modeling:** Huber Regression (production), LightGBM/XGBoost (benchmarking)
- **Data/ML:** Python, pandas, scikit-learn
- **Pipeline:** Modular preprocessing, feature engineering, training, deployment scripts
- **Serialization:** Portable JSON model artifacts
- **Deployment:** Docker-ready setup with timestamped forecast outputs

---

## Methodology & Visualization

### Time-Series Split Strategy

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/groundwater/10_train_val_test_split.png" alt="Chronological train validation test split" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

- Chronological split: 70% train / 15% validation / 15% test
- Walk-forward evaluation to preserve real-world forecasting constraints
- No shuffle, no leakage

### Feature Engineering

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/groundwater/15_feature_importance.png" alt="Feature importance analysis" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

I engineered 44 features across lag, rolling statistics, seasonality, volatility, precipitation, and interaction groups, then selected a robust subset for production reliability.

---

## Evaluation Results

<div class="stats-grid">
  <div class="stat-box">
    <div class="stat-value">1.48m</div>
    <div class="stat-label">Avg MAE (Huber)</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">1.29m</div>
    <div class="stat-label">7-day MAE</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">1.12m</div>
    <div class="stat-label">14-day MAE</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">44</div>
    <div class="stat-label">Engineered Features</div>
  </div>
</div>

### Baseline and Model Comparison

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/groundwater/11_baseline_model_comparison.png" alt="Baseline and model comparison" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

- Huber delivered the best stability under limited-data conditions
- LightGBM and XGBoost were tested but less consistent on out-of-sample behavior
- Ensemble variants were evaluated and did not outperform the selected production setup

---

## Production Deployment

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/groundwater/17_production_deployment_summary.png" alt="Production deployment summary" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

### Runtime Capabilities

- Multi-horizon forecasts (7/14/21/28 days)
- Prediction intervals and confidence tags
- Alert levels for operational risk monitoring
- Conservative mode during high-volatility regimes
- Structured JSON outputs for downstream consumption

---

## Impact

- Delivered a practical forecasting system for groundwater planning workflows
- Improved short-horizon performance versus persistence baselines
- Established a reproducible ML workflow from preprocessing to deployment
- Produced client-ready outputs with interpretable uncertainty signals

---

## My Role

I owned the end-to-end implementation:

- Time-series experimentation and baseline design
- Feature engineering and model selection
- Production scripting and deployment logic
- Monitoring framework and technical documentation

---

## Note

This work was developed for a client engagement via Upwork. The shared page presents non-sensitive architecture, methodology, and results.

</div>
