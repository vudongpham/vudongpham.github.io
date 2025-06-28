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

This post summarises my presentation at the [Living Planet Symposium 2025](https://lps25.esa.int/) (Vienna, 26 June 2025).

- 💾 **Data publication:** <https://www.nature.com/articles/s41597-024-04062-w>  
- 📖 **Methodology publication:** <https://www.sciencedirect.com/science/article/pii/S1569843224002218>

### **Mapping land-cover and crop types requires dense Sentinel-2 time-series**

- **Sentinel-2** imagery has been available since 2015, offering a five-day revisit cycle.<br><br>
- Mapping historical crop types is difficult because the older **Landsat** archive provides a much coarser temporal resolution.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i2.webp" class="img-fluid rounded z-depth-1" %}<br>

### **The temporal-transferability challenge**

- Deep learning (DL) has become ubiquitous in remote sensing over the past decade.<br><br>
- Most training data have been collected during the Sentinel-2 era.<br><br>  
- Consequently, DL models trained on dense Sentinel-2 series must often be transferred to periods when only Landsat data are available.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i3.webp" class="img-fluid rounded z-depth-1" %}<br>

### **Conventional gap-filling methods degrade over time**

- Accurate crop mapping demands gap-free phenological trajectories.<br><br>  
- Numerous temporal gap-filling algorithms exist, each with specific strengths and weaknesses.<br><br>  
- Nevertheless, a model calibrated on dense Sentinel-2 data performs poorly when applied—unchanged—to sparser Landsat series.<br>

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i4.webp" class="img-fluid rounded z-depth-1" %}<br>

### **Temporal Encoding: a universal time-series representation**

- For each year, we allocate a 365-element vector corresponding to every day of the year.<br><br>  
- Each clear observation is inserted at the position matching its acquisition date.<br><br>  
- Unobserved days filled with **0** value —there is **no interpolation**, **no resampling**, **no parameterization** and **raw data is preserved**.<br>  

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i5.webp" class="img-fluid rounded z-depth-1" %}<br>

If visualised as a 2-D image, a temporally encoded series appears as follows:

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/e1.gif" class="img-fluid rounded z-depth-1" %}<br>

### **Why preserving raw information is important**

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i6.webp" class="img-fluid rounded z-depth-1" %}
{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i7.webp" class="img-fluid rounded z-depth-1" %}<br>

### **Temporal Encoding provides an equidistant feature space for diverse DL architectures**

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i8.webp" class="img-fluid rounded z-depth-1" %}<br>

### **Mapping results**

- The approach yields annual land-cover maps from 2000 to 2022 at continental scale.<br><br>  
- Detailed information on croplands and peatlands.

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/i9.webp" class="img-fluid rounded z-depth-1" %}<br>

### **Land-cover monitoring examples**

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/e2.gif" class="img-fluid rounded z-depth-1" %}

**Example 1 – Crop rotation in Poland (2000–2022).**
It is noted that the deep model was trained on crop reference data from only three years (2019, 2021, 2022), yet generalized across two decades.

{% include figure.liquid loading="eager" path="assets/img/posts/bsrlc_plus/e3.gif" class="img-fluid rounded z-depth-1" %}

**Example 2 – Peatland mining in Estonia (2000–2022).**