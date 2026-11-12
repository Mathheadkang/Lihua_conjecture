---
type: idea
title: >-
  Averaged DCL via background rigidity; the deterministic-curve DCL
  counterexample needs line-hugging over U^2 log-scales and uses both signs
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - gaussian_bh_one_sided_sharp_upper
tags:
  - independent-blocks
  - deficit-curve
---

Driver's synthesis after plan_two_sided_central_deficit_curve_lei_20261105 failed at DCL (heuristic, not proved).

1. What the failure shows. The curve reduction (step 3, proved) says a background acts on a null only through the monotone deficit curve D*(k) = min_{j>=k}(j-1-beta(j)). The deterministic-curve DCL is false: with 2n loading-one mates at means +-(1+r)w_j and D*(k) = min{k-1, n+m(k)}, both signs of z cross at the tilt-matched level |z|/r, giving 2 gamma_r U/(2 sqrt(2 pi)). The construction needs D* to vary by a factor at most 2 over k in [N exp(-U^2(r^-2-1)/2), N], i.e. the background count must stay within O(n) of the BH line over about U^2 scales of log k.

2. Why a real background should not do this (to be proved). Given its own factors x, a loading-one background block is a deterministic staircase, but shifting x_h by delta moves its count at level u by a factor about e^{u delta}; hugging across levels u in [U, U/r] then survives only for |x_h| within O(1/U) of the designed value, probability O(1/U), so its contribution to Delta^c is O(1), not O(U). Sums over many independent blocks concentrate (LLN) to a Gaussian-smoothed unit-variance mixture, and idea_a4ba452bf4a7 (MLR rigidity, numerics only) says such mean counts cannot hug the line over a tilt range longer than O(eta u/U^2); realized fluctuations return to the line only inside O(1/U) tilt windows (sibling counterexample scope). So the averaged statement E_x[Delta^c(D*(.;x))] <= U/(2 sqrt(2 pi)) + o(U) is plausible.

3. Proposed KEY lemma (averaged DCL). Split the curve's level range into tilt windows of length about 1/U. On windows where D* grows by at least a factor 24 per tilt distance d (Lei's exclusion (229)), Lei's exclusion applies and the two signs share one budget. Prove that the expected total tilt length of 'flat' windows (growth below that rate), weighted by phi(z) rho_r, is o(U) uniformly over all block backgrounds, using (a) shift sensitivity for loading-one blocks, (b) MLR rigidity for averaged counts, (c) at most J plateau right ends cost J (proved). This is a statement about the background law, not about deterministic curves, and does not need per-level anti-concentration.

4. One-sided consequence. The DCL counterexample uses both signs of z (positive-side mates are near mates for one sign and far mates for the other). In the one-sided problem only z > 0 inflates the null, so the deterministic-curve DCL with slope gamma_r may actually hold there; the one-sided block-class theorem could then reduce to Lei's Lemmas 4.5-4.7 with the line replaced by the curve plus the exponentially-many-blocks step B6'. Worth testing numerically first (one-sided version of flat2.py).
