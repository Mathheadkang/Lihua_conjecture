---
type: idea
title: Bounded higher-rank null-mean paired screen found no FDR increase
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - one-sided
  - composite-null
  - monotonicity
  - remote-simulation
  - search-round-2
---

Supporting investigation of idea_1425d6ce283f; official search round 2 slot 1. UC Davis-only run used one Python process and BLAS1, 15.63 seconds scientific runtime. Screened 240 signed-factor/residual Gaussian models with m in {4,6,8}, factor columns 2–5, residual variances {0,.02,.15,.5}, singular and interior PSD unit-diagonal covariance, and mixed true/false nulls. Covariance, alternative means and the true-null set were held fixed; coordinate 0 was changed from 0 to −δ, δ in {.2,.5,1,1.75}. Five finite q levels {.05,.1,.2,.35,.5}, n=24,000 paired/common-random-number samples per model: all 4,800 estimated differences were negative.

The largest screen difference selected before heldout was model 86, m=8, rank 4, residual 0, q=.05, θ=(0,0,0,0,0,0,0,1.5), shifted coordinate 0 to −.2. Independent heldout n=2,500,000 gave FDR(0)=.03442942 and FDR(−.2)=.0325790866667, paired Δ=−.00185033333333, MCSE=.0000202709514080, 95% interval [−.00189006439809,−.00181060226857]. No auxiliary Gaussian monotonicity counterexample found; neither a monotonicity theorem nor an asymptotic main-target refutation follows. No candidate written.

Exact code, config/seeds (screen 202611040611; heldout 202611040977), environment, all model parameters, screen aggregates, heldout batch aggregates, summary and SHA256SUMS preserved at /home/mingshuo/remote/lihua_conjecture_20261103_7447c4cf/null_mean_probe_20261104_e18DQO and downloaded to /private/tmp/lihua_null_mean_probe_20261104_e18DQO/remote_snapshot. All downloaded hashes verified; script SHA256 8cf76d4ebef755c0bad19d5325af69bc9fde7b9b39ead53f0d25640ef47ea7cf.
