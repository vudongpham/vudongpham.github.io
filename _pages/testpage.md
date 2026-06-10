---
layout: page
permalink: /testpage/
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
published: false
---

<style>
  .page-about { max-width: 1080px; margin: 0 auto; }
  .about-hero,
  .about-card,
  .about-publications { border: 1px solid var(--global-divider-color); border-radius: 0.75rem; }
  .about-hero { padding: 2rem; margin-bottom: 2rem; }
  .about-hero-grid,
  .about-method { display: grid; grid-template-columns: 2fr 1fr; gap: 1.5rem; }
  .about-kicker { font-size: 0.85rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.06em; }
  .about-title { margin-top: 0.35rem; }
  .about-actions,
  .about-tags,
  .about-links { display: flex; flex-wrap: wrap; gap: 0.5rem 1rem; }
  .about-profile ul { margin-bottom: 0; }
  .about-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; }
  .about-card,
  .about-publications { padding: 1.25rem; }
  .about-section { margin-top: 2.5rem; }
  .about-method { margin-bottom: 1rem; }
  .about-method-title { border-right: 1px solid var(--global-divider-color); padding-right: 1rem; }
  .about-tag { font-size: 0.85rem; }

  @media (max-width: 768px) {
    .about-hero-grid,
    .about-method,
    .about-grid { grid-template-columns: 1fr; }
    .about-method-title { border-right: 0; border-bottom: 1px solid var(--global-divider-color); padding-right: 0; padding-bottom: 1rem; }
  }
</style>

<section class="page-about">

  <section class="about-hero">
    <div class="about-hero-grid">
      <div>
        <p class="about-kicker">Machine Learning · Deep Learning · Earth Observation</p>
        <h1 class="about-title">Scalable AI for continental land-cover mapping</h1>
        <p>
          I am a researcher and PhD working at the interface of <strong>deep learning, remote sensing, and geospatial data engineering</strong>. At the
          <a href="https://geo.uni-greifswald.de/en/chairs/geographie/translate-to-english-fernerkundung-und-geoinformationsverarbeitung/" target="_blank" rel="noopener noreferrer">EO Lab, University of Greifswald</a>,
          I develop transferable models, large-scale datasets, and operational workflows for consistent land-cover characterization across extensive spatial and temporal domains.
        </p>
        <p class="about-actions">
          <a href="/publications/">Publications</a>
          <a href="#research-pillars">Research focus</a>
          <a href="#method-highlights">Method highlights</a>
        </p>
      </div>

      <aside class="about-profile">
        <p class="about-kicker">Research profile</p>
        <ul>
          <li>Continental-scale land-cover and land-use mapping from satellite image time series.</li>
          <li>Transferable ML/DL models for robust Earth observation across regions, sensors, and years.</li>
          <li>HPC and cloud-native pipelines for scalable inference, validation, and dataset production.</li>
        </ul>
      </aside>
    </div>
  </section>

  <section class="about-section" id="research-pillars">
    <h2>Research pillars</h2>
    <p>
      My work combines methodological innovation with production-scale Earth observation systems.
    </p>

    <div class="about-grid">
      <article class="about-card">
        <p class="about-kicker">Modeling</p>
        <h3>ML/DL for satellite time series</h3>
        <p>Temporal encoding, augmentation, patch-based learning, regression-based unmixing, and neural approaches for multi-class land-cover products.</p>
      </article>

      <article class="about-card">
        <p class="about-kicker">Generalization</p>
        <h3>Transferability and domain adaptation</h3>
        <p>Methods designed to remain stable across biogeographic gradients, acquisition conditions, sensors, and long temporal baselines.</p>
      </article>

      <article class="about-card">
        <p class="about-kicker">Systems</p>
        <h3>Scalable EO data engineering</h3>
        <p>Distributed processing, high-performance computing, cloud deployment, and reproducible pipelines for continental-scale EO applications.</p>
      </article>
    </div>

    <p class="about-tags">
      <span class="about-tag">Remote sensing applications</span>
      <span class="about-tag">Algorithm development</span>
      <span class="about-tag">Time-series analysis</span>
      <span class="about-tag">Model transferability</span>
      <span class="about-tag">Domain adaptation</span>
      <span class="about-tag">HPC and distributed computing</span>
    </p>
  </section>

  <section class="about-section" id="method-highlights">
    <h2>Method highlights</h2>
    <p>
      Selected methods and datasets I created or led, with links to publications and downstream applications.
    </p>

    <article class="about-card about-method">
      <div class="about-method-title">
        <p class="about-kicker">Method 01</p>
        <h3>Multi-class neural network regression</h3>
      </div>
      <div>
        <p class="about-tags">
          <span class="about-tag">Fractional cover</span>
          <span class="about-tag">Neural regression</span>
          <span class="about-tag">Spectral unmixing</span>
        </p>
        <p>
          Quantifies land-cover fractions through neural-network regression and regression-based unmixing, supporting more nuanced land-cover characterization than hard class assignment alone.
        </p>
        <p class="about-links">
          <a href="https://doi.org/10.1016/j.rse.2024.114206" target="_blank" rel="noopener noreferrer">Publication DOI</a>
          <a href="https://doi.org/10.1016/j.rse.2025.114740" target="_blank" rel="noopener noreferrer">Application 1</a>
          <a href="https://doi.org/10.1016/j.rse.2025.114646" target="_blank" rel="noopener noreferrer">Application 2</a>
        </p>
      </div>
    </article>

    <article class="about-card about-method">
      <div class="about-method-title">
        <p class="about-kicker">Method 02</p>
        <h3>Temporal encoding and deep-learning augmentation</h3>
      </div>
      <div>
        <p class="about-tags">
          <span class="about-tag">Time series</span>
          <span class="about-tag">Augmentation</span>
          <span class="about-tag">Transfer learning</span>
        </p>
        <p>
          Encodes raw satellite time series and combines them with augmentation strategies to improve transferability in land-cover mapping across spatial and temporal domains.
        </p>
        <p class="about-links">
          <a href="https://doi.org/10.1016/j.jag.2024.103867" target="_blank" rel="noopener noreferrer">Publication DOI</a>
          <a href="https://doi.org/10.1038/s41597-024-04062-w" target="_blank" rel="noopener noreferrer">Application</a>
          <a href="/blog/2025/BSRLC-Plus/" target="_blank" rel="noopener noreferrer">Technical blog</a>
        </p>
      </div>
    </article>

    <article class="about-card about-method">
      <div class="about-method-title">
        <p class="about-kicker">Method 03</p>
        <h3>Super-resolution and center-patch classification</h3>
      </div>
      <div>
        <p class="about-tags">
          <span class="about-tag">Super-resolution</span>
          <span class="about-tag">Patch context</span>
          <span class="about-tag">Urban mapping</span>
        </p>
        <p>
          Enhances historical Landsat observations toward 10-m spatial detail and uses contextual patch learning to classify center pixels from surrounding spatial patterns.
        </p>
        <p class="about-links">
          <a href="https://doi.org/10.1016/j.rse.2026.115251" target="_blank" rel="noopener noreferrer">Publication DOI</a>
          <a href="https://zenodo.org/records/17413880" target="_blank" rel="noopener noreferrer">Dataset/application</a>
          <a href="/blog/2025/BSRLC-Urban/" target="_blank" rel="noopener noreferrer">Technical blog</a>
        </p>
      </div>
    </article>
  </section>

  <section class="about-section about-publications">
    <h2>Publications</h2>
    <p>
      See peer-reviewed work on deep learning for Earth observation, land-cover mapping, time-series modeling, and scalable geospatial data production.
    </p>
    <p><a href="/publications/">Open publication list</a></p>
  </section>

</section>
