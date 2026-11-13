---
type: decision
title: 'New direction: gaussian_frozen_ray_order_bound'
kind: direction
target: gaussian_frozen_ray_order_bound
reason: autonomous
failed_plans_at_direction:
  - plan_gaussian_frozen_ray_order_bound_coarea_fisher_overlap
  - plan_gaussian_frozen_ray_order_bound_planted_line_tracking
rounds: 3
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:40:16.034Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

Both failed plans reduce the bound to one missing two-scale estimate (a log-scale occupation bound for the tilted log-likelihood, or short tracking of the maximizing scale). Single-scale identities and alignment-only convexity cannot give it. Next plans must use the mobility of the maximizing scale along the planted line (implicit-function derivative of the maximizer, with degenerate maxima handled separately) or the upcrossing co-area bound min(c,Lambda)-1 <= integral of (d_w L_w)_+ 1{1<L_w<c} dw, or a maximal Ornstein-Uhlenbeck regularization comparing curvature at one scale under the tilt of a later one. Reuse the proved steps 1-6 of both plans.
