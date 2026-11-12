---
type: idea
title: >-
  Sharpened admissibility and a no-double-witness bound in place of the
  pointwise H-blocking inequality
status: draft
idea_kind: approach
origin: researcher
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags: []
---

Execution of plan_two_sided_coordinate_carrier_blocking_20261105 stopped at its KEY core 2d. Two findings for a future plan. (1) Any argument that uses only the outer admissibility condition (212) with Lei's constants 1/2 and 3 cannot prove the pointwise blocking display (1-eta) h(t) + h(t+Delta_q) <= gamma(P_t) + eta: for the (212)-defined sets the display is false in an extreme-value family (d = 1/Phibar(w*) identical loading-one staircase blocks, the null alone in its block), where the left side reaches 1.17-1.34 at q = 1e-16 and 1.18-1.33 at q = 1e-30 while gamma(P_t) = 1. The gap is the looseness of (212): with the good-event constants sharpened to 1 +/- eps the same sums fall to 0.81-0.97 (one value 1.03). The rank lemma allows this sharpening for ranks k > J at cost sum_k 2 exp(-c eps^2 k), harmless for eps = U^{-1/8}, J = ceil(sqrt U). (2) The union over x-dependent carriers has no mechanism; the monotone-set boundary heuristic fails for M = {max_h x_h >= c}, whose coordinate boundary layer of width delta has measure about delta sqrt(2 log d)/e. Suggested replacement: prove a no-double-witness bound gamma{x in P_t : (sigma t, x) is an H-point and (sigma(t+Delta_q), x) is tracking} <= eta(q), which yields the display through gamma(A) + gamma(T') = gamma(A u T') + gamma(A n T') without any union over carriers. Heuristics: in the frozen extreme-value regime the total ratio at the first witness must lie in [1-eps, 1+eps], a Gumbel window of length O(eps) for the extreme factor; in the self-averaging regime the x-averaged count is a unit-variance mixture and MLR rigidity forbids two witnesses Delta_q/r apart. Open: mixed regimes, non-identical blocks, and the A/L share of the total count. Numerics are evidence only; the integrated H-densities of all D1 families stayed below 0.45 per sign at K = 0.5, so H-KEY itself remains plausible.
