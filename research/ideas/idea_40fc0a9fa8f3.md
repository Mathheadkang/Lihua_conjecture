---
type: idea
title: Resolve zero-mean mixed-tag boundary by positive shifts and rational weights
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_quadratic_penalized_population_maximizers
tags:
  - boundary-approximation
  - canonical-populations
---

A proof step suggested by the round-1 failed boundary counterexample: for a finite mixture supported at zero mean with either tag, preserve the true-null atoms at zero and move each alternative-tagged atom to a positive mean delta_n tending to zero. Retain all unit directions. Approximate the finitely many positive mixture weights by positive rational weights with total mass one. A tag-respecting coupling gives W_1 convergence; every resulting mean has absolute value at most delta_n, so the second moment tends to the original zero second moment. Under the approved continuity theorem's exact fixed-q, fixed-positive-loading, finite-dimensional hypotheses this also yields FDR convergence. This resolves this finite boundary family only. General P_2 approximation still needs separate truncation, quantization, and rationalization with second-moment control; W_1 continuity alone is insufficient. Source: the current round-1 search-summary pack and its failed zero_mean_mixed_tags candidate line.
