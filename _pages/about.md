---
layout: about
title: About
permalink: /
subtitle: 

nav_order: 1
news: false
selected_papers: false
social: true
---

<style>
  .page-about {
    font-family: "Inter", "Roboto", "Helvetica Neue", Arial, sans-serif;
    line-height: 1.7;
    color: #222;
    max-width: 900px;
    margin: 0 auto;
    padding: 10px 5px 40px 5px;
  }

  .section-title {
    font-size: 1.9rem;
    font-weight: 700;
    margin-top: 40px;
    margin-bottom: 15px;
    letter-spacing: 0.02em;
    color: #0b0b0b;
  }

  .about-lead {
    font-size: 1.08rem;
    margin-bottom: 25px;
    text-align: justify;
  }

  .keyword {
    font-weight: 600;
    color: #0047cc;
  }

  .about-link {
    font-weight: 500;
    color: #0055dd;
    text-decoration: none;
    border-bottom: 1px solid #cfe0ff;
    transition: 0.2s;
  }
  .about-link:hover {
    color: #003a99;
    border-bottom-color: #99baff;
  }

  .research-list {
    font-size: 1.05rem;
    padding-left: 20px;
    margin-top: 5px;
    margin-bottom: 25px;
  }
  .research-list li {
    margin-bottom: 6px;
  }

  .section-divider {
    border: none;
    height: 1px;
    background: linear-gradient(to right, #ccc, #eee, #ccc);
    margin: 30px 0;
  }

  .publications-link {
    font-size: 1.08rem;
    margin-top: 12px;
  }

 /* Highlights section */
  .highlights-section {
    margin-top: 24px;
  }

  .highlights-subtitle {
    font-size: 0.98rem;
    margin-bottom: 8px;
    color: #4b5563;
  }

  /* Clean table styling */
  .highlights-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 12px;
    font-size: 0.98rem;
  }

  .highlights-table thead {
    background: #f8f9fc;
  }

  .highlights-table th {
    text-align: left;
    padding: 10px 12px;
    font-weight: 600;
    border-bottom: 1px solid #d4d9e3;
    color: #6b7280;
    letter-spacing: 0.02em;
    white-space: nowrap;
  }

  .highlights-table td {
    padding: 10px 12px;
    vertical-align: top;
    border-bottom: 1px solid #eceff4;
  }

  .highlights-table tbody tr:nth-child(odd) {
    background: #fafbff;
  }

  .highlights-table tbody tr:hover {
    background: #f2f5ff;
  }

  .highlights-table td:first-child {
    font-weight: 600;
    color: #1d4ed8;
    width: 20%;
  }

  .highlights-table td a.about-link {
    font-weight: 600;
  }

  /* Mobile */
  @media (max-width: 768px) {
    .highlights-table {
      font-size: 0.92rem;
    }
  }

</style>

<section class="page-about">

  <section class="about-section">
    <h2 class="section-title">About Me</h2>
    <p class="about-lead">
      I am a researcher and PhD specializing in <span class="keyword">continental-scale land-cover mapping</span> and <span class="keyword">deep learning for Earth observation</span>. At the <a class="about-link" href="https://geo.uni-greifswald.de/en/chairs/geographie/translate-to-english-fernerkundung-und-geoinformationsverarbeitung/" target="_blank" rel="noopener noreferrer">EO Lab, University of Greifswald</a>, I work on scalable and consistent land-cover characterization across extensive spatial and temporal domains. My work integrates research and engineering by developing transferable geospatial models and datasets and deploying them on high-performance computing (HPC) and cloud infrastructures.
    </p>
  </section>

  <hr class="section-divider" />

  <section class="highlights-section">
    <h2 class="section-title">Highlights</h2>
    <p class="about-lead highlights-subtitle">I am the creator of:</p>
    <div class="highlights-table-wrapper">
      <table class="highlights-table">
        <thead>
          <tr>
            <th>Method</th>
            <th>Description</th>
            <th>Publication</th>
            <th>Application</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Multi-classes Neural Network regression</td>
            <td>This method quantifies land cover fractions using Neural Network and regression-based unmixing.</td>
            <td><a href="https://doi.org/10.1016/j.rse.2024.114206" class="about-link" target="_blank" rel="noopener noreferrer">DOI</a></td>
            <td>
              <a href="https://doi.org/10.1016/j.rse.2025.114740" class="about-link" target="_blank" rel="noopener noreferrer">1</a>,
              <a href="https://doi.org/10.1016/j.rse.2025.114646" class="about-link" target="_blank" rel="noopener noreferrer">2</a>
            </td>
          </tr>
          <tr>
            <td>Temporal Encoding and deep learning augmentations</td>
            <td>
              This method encodes raw time-series, combined with augmetation methods to enhance land cover mapping's transferability. Read more in this 
              <a href="/blog/2025/BSRLC-Plus/" class="about-link" target="_blank" rel="noopener noreferrer">blog.</a>
            </td>
            <td><a href="https://doi.org/10.1016/j.jag.2024.103867" class="about-link" target="_blank" rel="noopener noreferrer">DOI</a></td>
            <td><a href="https://doi.org/10.1038/s41597-024-04062-w" class="about-link" target="_blank" rel="noopener noreferrer">1</a></td>
          </tr>
          <tr>
            <td>Super-resolution and center-patch classification</td>
            <td>
              The super-resolution methods enhances the spatial resolution of historical Landsat data to 10-m. The center-patch classification learns the contexts of the surrounding to classify the center pixel. Read more in this 
              <a href="/blog/2025/BSRLC-Urban/" class="about-link" target="_blank" rel="noopener noreferrer">blog.</a>
            </td>
            <td>DOI</td>
            <td><a href="https://zenodo.org/records/17413880" class="about-link" target="_blank" rel="noopener noreferrer">1</a></td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
  <hr class="section-divider" />

  <section class="research-section">
    <h2 class="section-title">Research Interests</h2>
    <ul class="research-list">
      <li>Large-scale remote sensing and geospatial analytics</li>
      <li>Methodological and algorithmic development</li>
      <li>Machine learning for Earth observation</li>
      <li>Model transferability and domain adaptation</li>
      <li>High-performance and distributed computing</li>
    </ul>
  </section>

  <hr class="section-divider" />

  <section class="publications-section">
    <h2 class="section-title">Publications</h2>
    <p class="publications-link">
      <a href="/publications/" class="about-link" target="_blank" rel="noopener noreferrer">
        See my current publication list
      </a>
    </p>
  </section>

</section>
