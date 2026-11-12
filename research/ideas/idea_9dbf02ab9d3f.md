---
type: idea
title: Held-out UC Davis multifactor BH probes did not reproduce screening inflation
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
  - multifactor_radial_fdr_bounds
  - directional_entropy_one_sided_fdr_bound
tags: []
---

Remote reproducibility artifacts: ucd-pkbh:/home/mingshuo/remote/lihua_conjecture_20261103_7447c4cf/multifactor_probe/ contains probe.py, config.json, environment.json, sanity.json, screen.json, validation.json, summary.json, validation_summary.txt. Python3.8 NumPy1.24.4 SciPy1.10.1; max2 workers, BLAS/OMP1. Exact largest-rank-hole, ties, boundary, R=0, singular identical/antipodal and unit variance checks passed. Independence global-null check: 100000 reps N16 q=.05, FDR .05032 MCSE .0006913. Screened18 angular/cone/tetrahedral/signed-axis d2/d3 models at N512, q=.01,.003,.001, 16000 reps/config. The selected cfg07 screening maxima at q=.001 had FDR/q1.1531(one) and1.3254(two), but independent240000-rep validation at same q gave .8046579, normal95 [.7444358,.8648799] (one) and .8644542 [.7883436,.9405647] (two). Conservative empirical-Bernstein per-row intervals also saved. No radial/entropy bound contradictions. Families were exploratory, not least-favorable constructions; saved draws are aggregate sufficient statistics, intervals are not simultaneous, and these finite-q outputs cannot establish or refute asymptotic constants. Supplied baselines.py separately passed on this remote server after the earlier connection timeout was resolved.
