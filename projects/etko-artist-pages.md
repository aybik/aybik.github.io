---
layout: single
title: "Automated Artist Page Generation"
permalink: /projects/etko-artist-pages/
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
  <h1>Automated Artist Page Generation</h1>
  <p class="project-subtitle">LLM-powered artist extraction and biography enrichment pipeline for Etko</p>
</div>

<div class="project-detail-page" markdown="1">

## Overview

I designed and integrated an automated pipeline that builds high-quality artist pages from event ingestion data.

The system has two core capabilities:

- Extracting artists from event/session text (concerts + stand-up)
- Generating artist descriptions and SEO metadata using LLM + external signals

This powers Etko's artist detail pages, follow features, search relevance, and SEO coverage.

---

## Problem

Etko ingests events from multiple external sources where artist data is often missing, inconsistent, or embedded in noisy free text.

At the same time, artist pages need meaningful descriptions and metadata to be indexable and useful.

This caused:

- Sparse artist-event relationships
- Incomplete artist pages
- Low SEO quality for long-tail artist traffic
- High manual enrichment overhead

### Constraints

- Mixed event formats across providers
- Turkish-heavy content with informal naming patterns
- Ambiguous session names (e.g., tribute, b2b, showcase formats)
- Need for production-safe confidence filters and deterministic persistence

---

<div class="highlight-box">
<p><strong>Solution:</strong> A production pipeline that maps sessions to artists via OpenAI extraction, persists normalized artist relations, then enriches artist bios + SEO fields using Spotify/Last.fm/Wikipedia/Google context.</p>
</div>

---

## Technical Stack

- **Extraction models:** OpenAI structured outputs (function calling)
- **Generation models:** `gpt-5-mini` for bios + SEO tags
- **Data pipeline:** Python ingestion/merge/mapper pipeline
- **Storage:** Supabase/Postgres with UUID entity graph
- **Serving layer:** RPC-backed artist APIs for web/mobile pages

---


## System Architecture

The artist page pipeline is integrated into the same ingestion lifecycle as event normalization.
<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/etko/artist-page-generation-flow.png" alt="Artist Page Generation Flow" style="max-width: 100%; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1rem; background: white;">
</div>


### Runtime Flow

1. Source sessions are crawled and parsed into canonical entities
2. Massken sessions/events are created and merged
3. Sessions missing artists are fetched by subcategory
4. LLM extraction maps session -> artist candidates
5. New artists are upserted, then `artists_sessions` is written
6. `create_artists_events()` derives event-level artist links
7. Artists without bios are selected by priority
8. Bio + SEO fields are generated and stored (`artists`, `artist_seo`)
9. Slugs/sitemaps/APIs expose artist pages to clients and search engines

---

## Data Model

### Core Tables

- `artists`: canonical artist identity + page content fields
- `artists_sessions`: session-level extracted mapping (`confidence`, `member`)
- `artists_events`: event-level derived mapping for page/event joins
- `artist_seo`: `seo_title` + `seo_description` per artist
- `user_artists`: follow graph for personalization + popularity signals

### Key RPCs / SQL Functions

- `create_artists_events()`
- `get_artists_without_bios(limit_count, standup_subcat)`
- `get_artist_v2(_slug, _base_url, _language)`
- `get_artists_sessions_v2(_slug, _upcoming, _base_url, _page, _page_size)`

---

## Artist Extraction

### Category-Aware Extraction Strategy

Two extractors run with separate prompts and validation logic:

- **Concert extractor** for music events
- **Stand-up extractor** for comedy/talk sessions

This separation improves precision by matching prompt behavior to domain language.

### Concert Extraction Details

The concert extractor supports:

- Function-call schema for structured artist output
- Confidence-based filtering
- Post-processing for tribute patterns
- B2B split logic (single title -> multiple artists)
- Member handling for groups/bands
- False-positive filtering (festival-like phrases, generic terms)

### Stand-up Extraction Details

The stand-up extractor applies:

- Prefix cleanup (show/generic wrappers)
- Flexible text validation against session name + description
- Duplicate prevention
- Confidence thresholding for noisy candidates

---

## Description & SEO Enrichment

After graph creation, artists lacking content are enriched in batches.

### Input Signals

For each artist, the pipeline combines external context from:

- Spotify (artist profile, top tracks, albums)
- Last.fm (bio snippets, tags)
- Wikipedia summaries
- Google Custom Search snippets

### Generation Outputs

The enricher writes:

- Long-form artist description
- SEO title
- SEO meta description

Stand-up and music paths use different prompts and context strategies.

### Safety & Quality Controls

- Skip updates if description generation is empty
- Update only non-disabled artists selected by priority
- Store SEO on separate `artist_seo` table (upsert on `artist_id`)
- Mark `ai_generated_description = true` on successful enrichment

---

## Production Integration

This is a production pipeline step, not a one-off script.
<div style="text-align: center; margin: 2rem 0;">
  <img src="/assets/images/projects/etko/artist-pipeline-flow.png" alt="Artist Pipeline Flow" style="max-width: 420px; height: auto; border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; background: white;">
</div>


### Integration Points

- Extraction is part of mapper flow after merge
- Event-level relationships are finalized with SQL RPC (`create_artists_events`)
- Enrichment is mapper-driven and runs with environment-based API credentials
- Slug/sitemap systems include only artist pages with valid content
- Web page serving uses `get_artist_v2` and `get_artists_sessions_v2`

### API and Page Layer

Artist pages consume enriched content through RPC-backed server endpoints and structured metadata generation:

- Canonical artist payload (name, image, description, SEO)
- Upcoming/past event lists for page sections
- JSON-LD (`Person` + `performerIn` events) for discoverability

---

## Impact

- **Automated artist identity extraction** from unstructured session text
- **Scalable artist-page generation** without manual writing
- **Improved SEO readiness** via generated artist metadata
- **Better discovery UX** for search, follows, and artist-event navigation

---

## My Role

I owned the end-to-end implementation of the artist page generation pipeline:

- Extraction architecture and post-processing logic
- AI-driven bio and SEO enrichment design
- Database function and RPC integration for serving layer compatibility

---

## Note

The production repository for this project is private. This page intentionally omits internal credentials, full schemas, and sensitive operational details. Technical descriptions are simplified representations of the deployed system.

</div>
