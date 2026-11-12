---
type: idea
title: Use the nonzero correlation-rotation check to calibrate signed face transport
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_correlated_clone_first_variation
tags:
  - correlated-clones
  - first-variation
  - signed-face-transport
  - search-round-3
---

Round 3's N = 2, K = 1 alternative-coordinate rotation has a nonzero exact Gaussian correlation derivative that agrees with the target's signed coordinate-face derivative; its NOT check fails. This only verifies the tested model, but it obstructs a proof shortcut that treats all rotations as zero-derivative perturbations or drops the dependence of the signed face jump on unchanged coordinates.

Proposed proof step: establish a local coordinate-face transport lemma for the original finite-grid BH FDP using the actual largest ranks and signed jumps. First truncate the Gaussian variables and marks. On bounded sets, isolate single-face crossings and prove that neighborhoods of intersections of distinct original threshold faces contribute o(epsilon), using positive definiteness rather than probability-zero intersections alone. Then justify tail removal and show that normalization of each perturbed score changes the first-order calculation by o(epsilon). The nonzero two-score correlation derivative is a calibration identity for this argument, not a proof of it. The separate all-or-none reduction for K > 1 still needs its fixed-grid Gaussian-tail argument.

Scope: this is an unproved approach for the fixed finite positive-definite original model. A fully coincident singular-original-face diagnostic is an unchecked extension risk outside the target, not an admissible counterexample and not a proof of a failure of the original conjecture.
