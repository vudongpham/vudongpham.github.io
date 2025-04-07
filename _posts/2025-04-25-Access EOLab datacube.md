---
layout: post
title: Access EOLab datacube
date: 2025-03-25 00:00:00
description: Access EOLab datacube
tags: formatting images
categories: sample-posts
map: true
images:
  compare: true
  slider: true

---

### 0. Readme

- FORCE Documentation: <a href='https://force-eo.readthedocs.io/en/latest/' target="_blank">Link</a>
- FORCE Github repo : <a href='https://github.com/davidfrantz/force' target="_blank">Link</a>
- How to access uni-greifswald brain cluster : <a href='https://rz.uni-greifswald.de/en/services/general/miscellaneous/high-performance-computing/login-to-hpc-brain-cluster/' target="_blank">Link</a>
  

### 1. Pull FORCE docker via singularity in HPC

```
module load singularity
singularity pull -F ~/force_latest.sif docker://davidfrantz/force:latest
```

### 2. Check the pulled image
Run to check if the image works
```
singularity exec ~/force_latest.sif force-info
```

### 3. Overview of existing data in the datacube:

Web viewer of EOLab datacube: <a href='https://vudongpham.github.io/EOLabDatacubeReport/' target="_blank">Link</a>

### 4. Access datacube and run FORCE:

- The `level2` data directory location (you only have read/execute rights) <br><br>
```
/home/phamv/edc/level2
```

- Whenever running FORCE process, `bind` the `level2`directory, for example:<br><br> 
```
singularity exec --bind /home/phamv/edc/level2 ~/force_latest.sif force-higher-level ...
```


