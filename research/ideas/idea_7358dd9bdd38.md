---
type: idea
title: >-
  Bounded rare offsets confine the actual population BH crossing to integer-rank
  layers
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_rare_clone_mills_variation
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Proof route to check, not an established general lemma. For the rare downward-offset law, the atom at zero has mass 1-epsilon L and all offsets lie in [0,epsilon/U]. Therefore its selected clone fraction b(x) is either zero or at least 1-epsilon L, unlike the smooth private-Gaussian profile. On a background-atom cell with r-1 selected unchanged groups and the chosen group present, a largest crossing lies in the layer [r-epsilon L,r]. Its birth threshold should be t_r(epsilon)=min_{v in [U,infinity]} {u(r-epsilon z(v))+epsilon c(v)}, where z(v)=(N/q){phi(v)/v-S(v)} and c(v)=1/U-1/v. Uniform first-order expansion gives u_r+epsilon min_v{A_r z(v)+c(v)}+O(epsilon^2), A_r=q/(N phi(u_r)); the derivative of the bracket is {1-A_r/A(v)}/v^2, so its minimum is at v=u_r and equals 1/U-m(u_r). Crucial missing general step: show the actual global largest crossing agrees in its integer layer with the finite surrogate using t_r on the chosen coordinate and u_r on others, outside background clipping strips. The strips for T_j are of width O(epsilon), while a changed chosen group requires T_i within O(epsilon) of some u_r; positive-definite joint densities should make their intersection probability O(epsilon^2), with constants allowed to depend on fixed N, q, Sigma, theta. Within a surviving layer the fractional FDP error is O(epsilon), supported on an O(epsilon) chosen-score band, giving O(epsilon^2) integrated error. Must handle r=N, the big zero-offset atom, no-rejection endpoint and nonstrict BH explicitly. The contact minimization alone is not the global-routing proof. Finite-copy quantile convergence also needs a separate argument excluding critical-level degeneracies almost surely.
