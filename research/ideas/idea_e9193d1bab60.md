---
type: idea
title: >-
  Use exact independent uniform-null block calibration as a cancellation
  benchmark for compensated clone variations
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_growing_clone_compensated_variation
tags:
  - growing-clones
  - signed-face-cancellation
  - search-round-3
---

Round 3 identifies a scoped proof-step benchmark. In the checked fixed model N=3, Sigma=I, theta=(1,0,0), q=1/4, with the nonzero alternative chosen for private cloning, exact null-block leave-out calibration gives finite-copy and common-population FDR 2q/3=1/6; every integrated original signed rank-face mass is zero. A possible proof step is to preserve the full signed FDP and calibrate independent uniform-null blocks before estimating local clone displacements: this exposes cancellations that a positive-face bound would lose. This calculation supports that step only in this independent model; it proves neither the general multirank expansion nor general population-endpoint convergence or clipping estimates. The empty-null model is a separate zero-FDP consistency check. Original means or covariance varying with epsilon are excluded by the fixed-model hypothesis and cannot supply an admissible counterexample here.
