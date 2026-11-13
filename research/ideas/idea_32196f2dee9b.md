---
type: idea
title: >-
  Simes acceptance at level 1/A forces M_A<0; each single scale k accepts with
  probability at least 1/2
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_mills_penalized_subset_supremum_acceptance
tags: []
---

Two steps toward gaussian_mills_penalized_subset_supremum_acceptance found in the round-1 boundary search. (1) Deterministic: if t_(j) < Phibar^{-1}(j/(NA)) for all j (Simes at level 1/A accepts), then sum_{j<=k} Phibar^{-1}(j/(NA)) <= NA phi(Phibar^{-1}(k/(NA))) = k tau_A(K), since int_0^p Phibar^{-1} = phi(Phibar^{-1}(p)). So M_A<0, and the lemma holds with delta0=1-1/A for independent and for nonnegatively correlated Sigma (lib_chi2024_positive_gaussian_simes). (2) For each fixed k, the single-scale maximum M^(k) is convex in the underlying Gaussian with mean <= tau_k(h(Phibar^{-1}(k/N)) - tau_k) < 0, using sum_K T_i <= ku + sum_i (T_i-u)_+. Ehrhard gives median <= mean, so P(M^(k)<=0) >= 1/2 for every Sigma. What remains is to control the maximum over the roughly log N dyadic scales of k under negative dependence.
