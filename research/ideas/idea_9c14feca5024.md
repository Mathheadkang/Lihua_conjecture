---
type: idea
title: >-
  Condition on unchanged statistics and transport signed largest-rank BH face
  jumps
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_correlated_clone_first_variation
tags:
  - clone-variation
  - signed-face-transport
  - proof-obligation
---

Round 4's failed counterexample suggests the following proof step, not an established general result. Condition on the unchanged statistics and describe the perturbed group's crossing of each original fixed threshold using its minimum mark. Keep the actual largest BH rank on both sides, including cascades, and integrate the signed FDP jump rather than its positive part. The tested independent N=3, K=2 model with means (0,1,0) and marks coupled to unchanged statistics has both signs of rank-three cascades; its exact conditional integrals agree with the claimed variation. The 60,000 numerical face checks are diagnostic only. For the general proof, establish exact-copy invariance at deterministic ties, derive the fixed-grid clone-spread implication and Gaussian-tail bound, then justify conditional threshold transport after truncating unbounded marks. Control shrinking neighborhoods of intersecting original threshold faces by o(epsilon), remove the normalized-score remainder, and justify integration/limit exchange. Positive definiteness and probability-zero face intersections alone do not establish those bounds. No arbitrary-covariance or arbitrary-marks identity is proved by the small-case check.
