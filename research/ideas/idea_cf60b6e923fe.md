---
type: idea
title: >-
  gaussian_simes_sparse_crossing_fixed_level_cap and
  gaussian_simes_sparse_positive_class_hitting differ
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_sparse_crossing_fixed_level_cap
  - gaussian_simes_sparse_positive_class_hitting
tags:
  - route
---

Both are fixed-level bounds on sparse Simes crossings, but neither implies the other alone. The cap bounds the whole sparse event S_q (thresholds below Phibar(u_q+1)) by 1-eta for every Sigma. The hitting lemma bounds only E minus D_{alpha,delta0} intersected with the event that a Sigma-dependent positive-class prior fails to hit the BH rejection set proportionally, by 1/4; it says nothing about crossings that are hit. It yields the cap only together with the positive-class cover transfer and the dense tilt bound (P(S) <= C_D alpha + 1/4 + alpha/(c c*)).
