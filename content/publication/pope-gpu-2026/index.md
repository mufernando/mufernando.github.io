---
title: GPU accelerated population genetics statistics using pg_gpu
authors:
- Nathaniel S. Pope
- Angel G. Rivera-Colón
- Ananya Kapoor
- Kevin Korfmann
- admin
- Scott T. Small
- Anastasia A. Teterina
- Andrew D. Kern
date: '2026-05-01'
publishDate: '2026-10-16T04:01:47.515524Z'
publication_types:
- manuscript
publication: '*bioRxiv*'
doi: 10.64898/2026.05.29.728868
abstract: 'Population genetics summary statistics—diversity, divergence, linkage disequilibrium,
  selection scans, and dimensionality reduction—are fundamental across human, agricultural,
  and ecological genomics. As whole-genome sequencing datasets have grown to hundreds
  of thousands of individuals, the cost of computing these statistics on conventional
  CPU implementations has become a major bottleneck: windowed scans of a single chromosome
  arm can take hours to days, and computation of pairwise linkage-disequilibrium statistics
  useful for demographic inference scales as O(n2) in sample size, often exceeding
  wall-clock budgets entirely. We present pg_gpu, a Python library implementing a
  comprehensive catalog of population-genetics summary statistics as fused CUDA kernels
  on NVIDIA GPUs. pg_gpu covers eleven categories spanning diversity and neutrality
  tests, divergence, admixture, the site-frequency spectrum, linkage disequilibrium,
  haplotype-based selection scans, dimensionality reduction (PCA, randomized PCA,
  local PCA / lostruct), distance distributions, relatedness, resampling, and a generalized
  weighted-SFS framework for custom ω estimators. On the full Ag1000G Phase 3 chromosome
  3R arm (2,940 haplotypes, 10.9 million variants) pg_gpu agrees with scikit-allel
  and PLINK2 to machine precision while delivering a median 139× and maximum 1,096×
  speedup. For the multi-population LD statistics used by moments for demographic
  inference, pg_gpu is a drop-in replacement that yields a ~1,750-fold speedup over
  the native implementation. Whole chromosome arm scans, lostruct screens, and calculation
  of LD statistics complete on a single NVIDIA A100 in seconds to a few minutes.'
links:
- name: URL
  url: https://www.biorxiv.org/content/10.64898/2026.05.29.728868v1
---
