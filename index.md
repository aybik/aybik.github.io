---
layout: single
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

body {
  font-family: 'Manrope', -apple-system, BlinkMacSystemFont, sans-serif;
  background-color: var(--bg-color);
  transition: background-color 0.3s ease;
  font-size: 16px;
}

h1, h2, h3, h4 {
  font-family: 'Space Mono', monospace;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: var(--text-dark);
}

.custom-intro {
  max-width: 850px;
  margin: 0 auto 2rem;
  padding: 0 1.5rem;
}

.custom-intro h1 {
  font-size: 1.85rem;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, var(--accent-teal), var(--accent-coral));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.3;
}

.custom-intro p {
  font-size: 0.95rem;
  line-height: 1.6;
  color: var(--text-dark);
  font-weight: 400;
  margin-bottom: 0.75rem;
}

.featured-projects {
  max-width: 1100px;
  margin: 1.5rem auto;
  padding: 0 1.5rem;
}

.section-header h2 {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  position: relative;
  display: inline-block;
}

.section-header h2::after {
  content: '';
  position: absolute;
  bottom: -6px;
  left: 0;
  width: 60%;
  height: 3px;
  background: linear-gradient(90deg, var(--accent-teal), var(--accent-coral));
  border-radius: 2px;
}

.project-card {
  background: var(--card-bg);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 4px var(--shadow-color), 0 8px 16px var(--shadow-color);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  margin-bottom: 2rem;
  border: 1px solid var(--border-color);
}

.project-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 8px var(--shadow-color), 0 12px 24px var(--shadow-color);
}

.project-card-header {
  background: linear-gradient(135deg, var(--primary-blue), var(--primary-dark));
  padding: 1.5rem 1.75rem;
  position: relative;
  overflow: hidden;
}

.project-card-header::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -10%;
  width: 250px;
  height: 250px;
  background: radial-gradient(circle, rgba(22, 160, 133, 0.12) 0%, transparent 70%);
  border-radius: 50%;
}

.project-card-header h3 {
  color: white;
  font-size: 1.15rem;
  margin-bottom: 0.65rem;
  position: relative;
  z-index: 1;
  line-height: 1.3;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  position: relative;
  z-index: 1;
}

.project-tag {
  background: rgba(255,255,255,0.15);
  backdrop-filter: blur(10px);
  color: white;
  padding: 0.25rem 0.65rem;
  border-radius: 15px;
  font-size: 0.75rem;
  font-weight: 500;
  border: 1px solid rgba(255,255,255,0.2);
}

.project-card-body {
  padding: 1.5rem 1.75rem;
}

.project-card-body p {
  font-size: 0.9rem;
  line-height: 1.55;
  color: var(--text-dark);
  margin-bottom: 0.85rem;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  color: var(--accent-teal);
  font-weight: 600;
  text-decoration: none;
  font-family: 'Space Mono', monospace;
  font-size: 0.85rem;
  transition: gap 0.3s ease;
  margin-top: 0.5rem;
}

.project-link:hover {
  gap: 0.65rem;
  color: var(--accent-coral);
}

.project-link::after {
  content: '→';
  font-size: 1.1em;
  transition: transform 0.3s ease;
}

.project-link:hover::after {
  transform: translateX(3px);
}

.dark-mode-toggle {
  position: fixed;
  bottom: 1.5rem;
  right: 1.5rem;
  background: #16a085;
  color: white;
  border: none;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  cursor: pointer;
  box-shadow: 0 3px 10px rgba(0,0,0,0.2);
  z-index: 1000;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.dark-mode-toggle:hover {
  transform: scale(1.08);
  background: #e94560;
}

.sidebar {
  background: var(--card-bg);
}

.page__content {
  color: var(--text-dark);
}

@media (max-width: 768px) {
  body {
    font-size: 15px;
  }

  .custom-intro h1 {
    font-size: 1.65rem;
  }

  .custom-intro p {
    font-size: 0.9rem;
  }

  .project-card-header,
  .project-card-body {
    padding: 1.25rem;
  }

  .section-header h2 {
    font-size: 1.35rem;
  }

  .dark-mode-toggle {
    bottom: 1rem;
    right: 1rem;
    width: 42px;
    height: 42px;
  }
}
</style>

<div class="custom-intro">
  <h1>Hi, I'm Aybike.</h1>
  <p>I work with applied data analysis and machine learning, bringing together perspectives from engineering and social sciences. I care deeply about data quality, transparent assumptions, and how analytical results translate into real-world decisions.</p>
  <p>My focus is on building ML systems that work in practice—not just in notebooks—with particular attention to evaluation frameworks that reflect actual deployment constraints.</p>
</div>

<div class="featured-projects">
  <div class="section-header">
    <h2>Featured Projects</h2>
  </div>

  <div class="project-card">
    <div class="project-card-header">
      <h3>Disclosure-Driven ML Trading (BIST)</h3>
      <div class="project-tags">
        <span class="project-tag">Event-Aware ML</span>
        <span class="project-tag">Time-Series CV</span>
        <span class="project-tag">Leakage Prevention</span>
        <span class="project-tag">Realistic Backtesting</span>
      </div>
    </div>
    <div class="project-card-body">
      <p>An end-to-end ML pipeline that transforms public company disclosures into tradable signals on Borsa İstanbul. Features rigorous leakage prevention, exchange-aware timestamp alignment, and portfolio-level evaluation that accounts for real trading constraints.</p>
      <p>This project demonstrates practical ML engineering: from messy real-world data to production-ready signals, with evaluation metrics that matter for actual deployment.</p>
      <a href="/projects/bist-ml-trading/" class="project-link">Explore the project</a>
    </div>
  </div>

  <div class="project-card">
    <div class="project-card-header">
      <h3>Automated Event Classification (Etko)</h3>
      <div class="project-tags">
        <span class="project-tag">BERT</span>
        <span class="project-tag">Turkish NLP</span>
        <span class="project-tag">Production System</span>
        <span class="project-tag">Class Imbalance</span>
      </div>
    </div>
    <div class="project-card-body">
      <p>A BERT-based NLP system that automatically classifies cultural events into 37 subcategories. Integrated into Etko's data ingestion pipeline, achieving 93% accuracy on Turkish-language events with smart handling of class imbalance through data-centric approaches.</p>
      <p>Powers event discovery, filtering, and SEO across multiple ticketing platforms with configurable confidence thresholds and continuous monitoring.</p>
      <a href="/projects/etko-event-classification/" class="project-link">Explore the project</a>
    </div>
  </div>
</div>

<button class="dark-mode-toggle" onclick="toggleDarkMode()">🌙</button>

<script>
function toggleDarkMode() {
  var body = document.body;
  var button = document.querySelector('.dark-mode-toggle');

  if (body.classList.contains('dark-mode')) {
    body.classList.remove('dark-mode');
    button.textContent = '🌙';
    try {
      localStorage.setItem('theme', 'light');
    } catch (e) {}
  } else {
    body.classList.add('dark-mode');
    button.textContent = '☀️';
    try {
      localStorage.setItem('theme', 'dark');
    } catch (e) {}
  }
}

window.addEventListener('load', function() {
  var savedTheme = 'light';
  try {
    savedTheme = localStorage.getItem('theme') || 'light';
  } catch (e) {}

  if (savedTheme === 'dark') {
    document.body.classList.add('dark-mode');
    document.querySelector('.dark-mode-toggle').textContent = '☀️';
  }
});
</script>
