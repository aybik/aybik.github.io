---
layout: single
title: "Automated Event Subcategory Classification"
permalink: /projects/etko-event-classification/
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
  <h1>Automated Event Subcategory Classification</h1>
  <p class="project-subtitle">Production NLP system for large-scale cultural event categorization</p>
</div>

<div class="project-detail-page" markdown="1">

## Overview

I designed and deployed a BERT-based NLP pipeline that automatically classifies cultural events (concerts, theatre, sports, exhibitions, etc.) into canonical subcategories.

The system is fully integrated into Etko's data ingestion pipeline and powers event discovery, filtering, and SEO category pages.

---

## Problem

Etko aggregates cultural events from multiple ticketing platforms. Each source uses its own category system, and many events arrive with missing or inconsistent categorization.

This caused:

- Broken category-based discovery
- Inconsistent filters across cities
- Manual labeling overhead
- Poor SEO category coverage

### Constraints

- Events are mostly in **Turkish**
- Titles and descriptions are noisy and unstructured
- Some subcategories have very few historical examples

---

<div class="highlight-box">
<p><strong>Solution:</strong> A supervised NLP classification system that learns semantic patterns from event titles and descriptions, predicts subcategories, and runs automatically as part of the ingestion pipeline.</p>
</div>

---

## Technical Stack

- **NLP Model:** BERT (Turkish) - `dbmdz/bert-base-turkish-cased`
- **Training:** HuggingFace Transformers
- **Inference:** Batch pipeline integrated into data ingestion
- **Storage:** Relational DB with UUID-based taxonomy
- **Max sequence length:** 512 tokens

---

## System Architecture

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/etko/event-classification-architecture.png" alt="Event Classification Architecture" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

The classification pipeline integrates seamlessly into Etko's data ingestion workflow, transforming raw event text into structured subcategory labels.

---

## Dataset & Labeling Strategy

### Multi-label to Single-label Transformation

Events could belong to up to two subcategories (e.g., *Rock* and *Music Festival*).

Instead of training a multi-label model immediately, I flattened the dataset:

- Each event with two labels became two training rows
- Identical text, different targets

This allowed me to:

- Train a simpler single-label classifier
- Achieve cleaner convergence
- Preserve ambiguity at inference time

### Handling Class Imbalance

Some subcategories (e.g., Opera, Improv Theater, niche sports) had very few real examples.

To address this, I applied a **data-centric approach**:

- Created realistic mock events with category-specific vocabulary
- Focused on semantic exposure, not metric inflation
- Avoided naive oversampling of identical samples

This helped the model learn underrepresented categories without distorting real-world distributions.

---

## Model Training

### Training Decisions

- Stratified train/validation/test splits
- Weighted F1 score as primary metric
- Early stopping to prevent overfitting
- Gradient accumulation to fit memory constraints

---

## Evaluation Results

<div class="stats-grid">
  <div class="stat-box">
    <div class="stat-value">93.4%</div>
    <div class="stat-label">Accuracy</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">0.93</div>
    <div class="stat-label">Weighted F1</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">0.92</div>
    <div class="stat-label">Macro F1</div>
  </div>
  <div class="stat-box">
    <div class="stat-value">37</div>
    <div class="stat-label">Subcategories</div>
  </div>
</div>

**Test set:** 1,964 events

Despite strong class imbalance and semantic overlap between some categories, the model maintains consistent performance across both high-frequency and low-frequency subcategories.

### Confusion Matrix

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/etko/confusion-matrix.png" alt="Confusion Matrix (Normalized, Test Set)" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>

The normalized confusion matrix reveals strong diagonal performance across most categories, with misclassifications concentrated primarily between semantically similar event types.

### Performance Highlights

- **Theater:** F1 = 0.98 (359 samples)
- **Stand-up & Talk Show:** F1 = 0.98 (147 samples)
- **Cinema:** F1 = 1.00 (61 samples)
- **Other Experiences:** F1 = 0.72 (high ambiguity, low support)

### Error Analysis

Most errors occur between semantically adjacent categories:

- Music subgenres (e.g., Rock vs. Pop vs. Electronic)
- Performing arts overlaps (e.g., Musical Theatre vs. Theatre)
- Sports categories are almost perfectly separated

The remaining classification errors primarily reflect genuine semantic ambiguity between event types rather than systematic model failure.

---

## Production Integration

The model is not a standalone demo—it is integrated as a **first-class pipeline step**.

<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/etko/pipeline-flow.png" alt="Pipeline Flow Architecture" style="max-width: 380px; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; background: white;">
</div>

### Runtime Flow

1. New source sessions are ingested
2. Sessions missing subcategories are selected
3. Trained model and tokenizer are loaded once per run
4. Batch inference runs on `name + description`
5. Predicted labels are mapped to canonical subcategory UUIDs
6. Results are written back to the database
7. All predictions are logged for monitoring

### Confidence Handling & Configurability

- The model always returns a top-1 prediction
- A second label is included only if confidence scores are close
- Thresholds are configurable via database settings
- No code redeploy required for tuning behavior

---

## Monitoring & Iteration

To support continuous improvement:

- All predictions and confidence scores are logged
- Low-confidence and misclassified cases are reviewed
- Insights are fed back into dataset improvements
- Models are retrained and redeployed as versioned artifacts

This creates a closed-loop system for quality improvement.

---

## Impact

- **Eliminated manual subcategory labeling** for new events
- **Enabled scalable category-based discovery** across all cities
- **Improved consistency** across multiple data sources
- **Supported SEO-friendly** category and city pages

---

## My Role

I owned the full lifecycle of this system:

- Dataset design and labeling strategy
- Model training and evaluation
- Production integration into the ingestion pipeline
- Monitoring and iteration workflow

---

## Note

The production repository for this project is private. This page intentionally omits internal code, credentials, and proprietary schemas. All descriptions are simplified representations of the deployed system.

</div>
