---
type: idea
title: >-
  Unit-variance backgrounds cannot hug the BH line over a tilt range (MLR
  rigidity)
status: resolved
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags: []
resolved_by: gaussian_unit_variance_mixture_hugging_rigidity
---

Planning observation (unproved; numerics only). For theta real put L_theta(u)=P(|theta+eps|>=u)/p(u), p=2*PhiBar, eps~N(0,1). Claim (i): u->log L_theta(u) is nondecreasing and star-shaped, d/du log L_theta(u) >= c1*log L_theta(u)/u for u>=1; pure-Python check on theta in (0,80], u in [1,49] gave min ratio 1.024 where log L>1. Claim (ii): for any finite mixture psi(u)=q*sum_l w_l L_{theta_l}(u), sum w_l<=1, psi is nondecreasing, and if U<=u_a<u_b, psi(u_a)>=1-eta>=1/2 and psi(u_b)<=1 then u_b-u_a <= C*eta*u_b/U^2 (U=p^{-1}(q)); 900 random mixtures at q=1e-6,1e-12,1e-24 gave C<=1.5. Reason: contributions with L<1/(4q) carry at most 1/4 of psi; the rest have log-slope >= c1*log(1/(4q))/u ~ U^2/(2u). Consequence: independent alternatives, and the factor-averaged law of any loading-one staircase block (unit-variance marginals), hug the BH line within relative eta only on a u-interval of length O(eta*u/U^2), i.e. a tilt (z=ru) length O(eta/U). So item 3 of idea_3370404c0baa ('a deterministic hugging background is realizable by LLN over a range') is false for any range of tilt length >> eta/U; long hugging needs factor-loaded (variance<1) components, which are sensitive to their own factor. Used as route (a) of the anti-hugging steps of plan_two_sided_coordinate_carrier_blocking_20261105.

Scope caveat. Claim (ii) concerns the mean count. Realized counts of an i.i.d. background fluctuate by relative order k^{-1/2} about the mean. A near-critical i.i.d. background therefore returns to the BH line with probability of order one, and per-cell return-probability bounds fail (the approved sibling counterexample in /Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent/research/assets/cx_block_extreme_window_lemma_r1_s2_critical_iid_background.md). Those returns stay inside the u-interval where the mean ratio is within O(k^{-1/2}) of one, so their tilt length is still O(1/U). The observation bounds tilt length only. It gives no return-probability bound.

## Resolution

Promoted to the lemma gaussian_unit_variance_mixture_hugging_rigidity, a dependency of gaussian_bh_one_sided_sharp_upper, gaussian_bh_two_sided_sharp_upper.
