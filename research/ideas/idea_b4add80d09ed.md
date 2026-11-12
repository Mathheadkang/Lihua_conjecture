---
type: idea
title: >-
  Lessons from the sibling project Lihua_conjecture_claude (approved there, not
  here)
status: resolved
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - gaussian_bh_one_sided_sharp_upper
tags:
  - sibling-project
  - independent-blocks
resolved_by: gaussian_sibling_factor_bounds_and_critical_background_obstruction
---

Source: /Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent/research/assets/ (read directly; the researcher pointed to it on 2026-11-05). Approval there does not transfer: any reuse must restate the result, cite the file, and reproduce the proof for verification here.

Approved there:
(1) onesided_direction_entropy_upper: one-sided K-factor model, loaded nulls grouped by direction with weights w_g. Then FDR <= q pi0 u/sqrt(2 pi) + Cq(1 + sum_g w_g log(1/w_g)). Sharp one-sided constant when log D_q = o(sqrt(log 1/q)); in particular for block one-factor models with log B_q = o(sqrt(log 1/q)).
(2) twosided_kfactor_sharp_upper (finite rank) and twosided_kfactor_growing_sharp_upper (K_q log log(1/q) = o(sqrt(log 1/q)); error q pi0 C[(K+1) log u + K^{1/4} u^{3/4}] + Cq): the sharp two-sided constant 1/(2 sqrt pi) in these classes.
(3) onesided/twosided_factor_width_upper_v2: width bounds via the null-direction maximum W (two-sided leading constant 1/sqrt pi, twice the target).
(4) cx_block_extreme_window_lemma_r1_s2_critical_iid_background: an approved counterexample to a per-cell return bound for the BH level process in many mixed-sign blocks. A critical i.i.d. background with mean count b - sqrt(b), plus one unit-loading null and about 10 sqrt(b) unit-loading non-nulls, makes a ratio->=s return in [b, sb) have probability bounded below. Per-cell anti-concentration against arbitrary independent backgrounds is false.

Open there: onesided_block_factor_sharp_upper (all B) is parked after five failed plans. The missing step is an anti-concentration (window) estimate in finitely many extreme factor coordinates across arbitrarily many mixed-sign blocks; block_carrier_excess_lemma (a pooled level-sum bound) is an unproved draft. This matches the B4 obstruction found here in plan_two_sided_exogenous_pivotal_blocks_20261105: two independent projects reached the same gap. Their general targets (one- and two-sided) are still open; their loop was at the plan stage for twosided_general_sharp_upper with 8 of 30 attempts spent.

## Resolution

Promoted to the lemma gaussian_sibling_factor_bounds_and_critical_background_obstruction, a dependency of gaussian_bh_one_sided_sharp_upper, gaussian_bh_two_sided_sharp_upper.
