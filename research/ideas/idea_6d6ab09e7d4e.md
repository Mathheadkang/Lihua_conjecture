---
type: idea
title: Fixed-grid clone-spread reduction with preserved labels
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_correlated_clone_first_variation
tags:
  - gaussian-bh
  - correlated-clones
  - fixed-grid
---

Prospective proof step from the round-5 search summary, not a proved result or new counterexample family. For a fixed finite expanded BH threshold grid, establish that any partial rejection of the perturbed i-group forces its clone-score spread to exceed a strictly positive grid gap. Use the actual largest qualifying BH rank, including non-strict inequalities and ties; the unchanged exact-copy groups must remain whole. Then bound the spread using the fixed Gaussian perturbation marks, retaining the normalization contribution of order epsilon squared times Z, to obtain the claimed Gaussian exponential exceptional probability. Check separately that when all groups are whole, the rejection set equals ordinary BH on the vector whose i-coordinate is the minimum clone score. The original null labels are preserved only under the stated sign restriction: if theta_i = 0 all c_b <= 0, and if theta_i is nonzero epsilon is sufficiently small to preserve its sign. These conditions make all-or-none rejection imply equality of the original and expanded FDPs. This route is already suggested by the board; round 5 supplies no new coverage. General remainder estimates, intersecting-face neighborhoods, and derivative integration remain unproved.
