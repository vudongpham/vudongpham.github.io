---
layout: post
title: BSRLC+ The first annual 30-m land cover maps with detailed crop types and peatlands in the Baltic Sea region over two decades (2000 – 2022)
date: 2025-06-26 00:00:00
description: Time-series land cover with detailed crop types and peatlands
tags: Temporal-encoding Deep-learning
categories: sample-posts
thumbnail: assets/img/posts/bsrlc_plus/thumbnail.webp
map: true
images:
  compare: true
  slider: true

---
{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i1.webp" class="img-fluid rounded z-depth-1" %}

This post summarises my presentation at the <a target="_blank" href="https://lps25.esa.int/">Living Planet Symposium 2025</a> (Vienna, 26 June 2025).

### **Mapping high-resolution (10 m) urban areas over two decades with Landsat data—Is it possible?**

- Landsat and Sentinel-2 are the principal sources of Earth-observation data for large-scale, long-term land-cover time-series analyses.<br><br>
- The fine spatial resolution (**10 m** in the visible bands) of Sentinel-2 is particularly advantageous for distinguishing built-up classes such as **residential buildings**, **industrial buildings**, and **artificial open spaces** (e.g. roads, railways).<br><br>
- Existing 10 m urban products—e.g. the <a target="_blank" href="https://human-settlement.emergency.copernicus.eu/download.php?ds=builtC">Global Human Settlement Characteristics</a> layer—depend on Sentinel-2 imagery and therefore cover only recent years.<br><br>
- How can we obtain equally detailed maps for earlier periods, when only Landsat imagery was available?<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i2.webp" class="img-fluid rounded z-depth-1" %}

### **Deep-learning super-resolution—Real-world deployment is harder than you think**

- Deploying deep-learning single-image super-resolution (SR) on Landsat data is not a new idea.<br><br>
- Most studies train SR models on temporally aligned Landsat/Sentinel-2 pairs and then apply the models to other Landsat scenes acquired under similar conditions.<br><br>
- In practice, applying SR models to historical Landsat imagery is complicated by issues such as the Landsat-7 SLC-off gaps, inter-scene spectral inconsistencies, and cloud contamination.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i3.webp" class="img-fluid rounded z-depth-1" %}

### **If real images are problematic, can synthetic composites help?**

- Spectral–temporal metrics (STMs)—statistics such as the minimum, maximum, median, or selected percentiles—aggregate information over time.<br><br>
- STM composites are spatially consistent across scenes.<br><br>
- In our recent <a target="_blank" href="https://www.sciencedirect.com/science/article/pii/S0034425724002244">study</a> we showed that impervious surfaces exhibit resilience to temporal variability, an asset for long-term mapping.<br><br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i4.webp" class="img-fluid rounded z-depth-1" %}

- By generating synthetic STM composites, we can harmonise Landsat and Sentinel-2 datasets in terms of both completeness and spectral characteristics.<br><br>
- This harmonisation enables an SR workflow that is suitable for multi-decadal mapping.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i5.webp" class="img-fluid rounded z-depth-1" %}

- We employ a single-image SRGAN architecture, training it on STM composites instead of raw imagery.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i6.webp" class="img-fluid rounded z-depth-1" %}

### **We have solved the resolution issue—Which classifier should we use?**

- Traditional **pixel-based** classification often struggles with urban scenes because different built-up types share similar spectral signatures at the pixel level.<br><br>
- **Patch-based** approaches leverage convolutional neural networks (CNNs) and spatial context, but at the cost of reduced output resolution.<br><br>
- Deep-learning **semantic-segmentation** models (e.g. U-Net) exploit spatial context while preserving resolution, but require exhaustive pixel-wise labelling—a labour-intensive task.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i7.webp" class="img-fluid rounded z-depth-1" %}

### **Centre-patch classification—Patch in, centre pixel out**

- Have only pixel-level reference data but need CNN-level spatial context without sacrificing resolution? Centre-patch classification is the answer.<br><br>
- It combines the strengths of **pixel-based** and **patch-based** approaches, functioning as a “lightweight” alternative to full semantic segmentation.<br><br>
- Training is simple: provide a sufficient number of pixel samples, and the network learns to classify the centre pixel of each patch.<br><br>
- We optionally add spatial-attention layers to guide the network, although they are unnecessary when ample training data are available.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i8.webp" class="img-fluid rounded z-depth-1" %}

### **Super-resolution results**

- The examples below illustrate STM-based SR applied to Landsat imagery.<br><br>
- In many urban areas, 30 m Landsat scenes are realistically up-scaled to 10 m.<br><br>
- In the third panel, road surfaces—largely absent in native Landsat—are convincingly synthesised in the 10 m output.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i9.webp" class="img-fluid rounded z-depth-1" %}

- Subsequent classification with 10 m SR imagery outperforms the same workflow conducted on 30 m imagery (up-scaled by nearest neighbour).<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i10.webp" class="img-fluid rounded z-depth-1" %}

### **Centre-patch classification performance**

- The figure below compares our results with those of the GHSC product.<br><br>
- **GHSC**: Sentinel-2 and OpenStreetMap inputs, pixel-based classification.<br><br>
- **Ours**: Sentinel-2 or Landsat inputs, centre-patch classification.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/i11.webp" class="img-fluid rounded z-depth-1" %}

### **The first large-scale, multi-temporal 10 m maps of built-up types in the Baltic Sea region**

Data are available on <a target="_blank" href="https://zenodo.org/records/14497660">Zenodo</a>.

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/e2.gif" class="img-fluid rounded z-depth-1" %}

*Berlin Brandenburg Airport construction (Berlin, Germany).*

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_urban/e1.gif" class="img-fluid rounded z-depth-1" %}

*Urban development over two decades (Poznań, Poland).*
