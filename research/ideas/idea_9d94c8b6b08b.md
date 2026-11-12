---
type: idea
title: Recover finite canonical moments by truncating before rationalizing weights
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_quadratic_penalized_population_maximizers
tags:
  - search-summary
  - moment-recovery
  - empty-null
---

Proof step suggested by the round-2 empty-null obstruction: for a finite-second-moment population supported on strictly positive means with all tags alternative, truncate means above R, quantize them to strictly positive values, and quantize directions on the fixed finite-dimensional unit sphere. Let R increase and the quantization meshes decrease so that the mean error tends to zero in L2; the second-moment tail controls truncation, while compactness controls directions. After each finite quantization, rationalize the finitely many positive weights, preserving total mass and making the total weight error negligible relative to both the maximum retained mean and its square. This yields W1 and second-moment convergence; all original and approximating FDRs are exactly zero, since the true-null mass is zero. Thus unbounded positive means with no true nulls are not an obstruction to canonical approximation. This is a proposed step for organizing the moment-recovery argument, not a proof of the target: mixed labels and completed zero-mean alternative points still require their own tag-respecting treatment and, for nonzero FDR, the exact approved fixed-loading continuity hypotheses.
