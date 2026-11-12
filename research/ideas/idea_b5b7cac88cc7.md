---
type: idea
title: >-
  Moving atoms invalidate the uniform-CDF step; trim the coupling and shift the
  common Gaussian score
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Correction to the optional proof route idea_f5243b60c394, identified independently by the plan worker; NOT a counterexample to the continuity target. Fix q,sigma>0 as in the target and one unit residual direction. Let pi be a true zero-mean atom and pi_n the same true atom shifted downward by delta_n>0. W1=delta_n->0 and the two scores are Y and Y-delta_n, with Y standard normal under the common field. Nevertheless on r in[a,1] their selection CDF step locations differ; the expected supremum of their H-discrepancy tends to q(1-a)>0, not zero. A finite grid plus unconditional marginal anti-concentration cannot control the supremum because the random jumps move between grid points. Do not use the claimed E sup H bound from that idea. Proposed replacement, now used by the pending plan: couple parameter laws, and condition on the residual Gaussian field. Score differences A=delta theta+sqrt(1-sigma²)X(delta v) do not involve the independent common Z. Remove coupling mass beta where |A|>e (and label mismatch when controlling V); E beta<=C W1/e plus label cost. On beta<=gamma, a qualifier at rank r>=a in one model transfers to rank r-gamma in the other after common shift h=(e+L_{q,a}gamma)/sigma, because threshold u(q(r-gamma))-u(qr)<=L_{q,a}gamma and good scores move by at most e. Apply both directions, then integrate monotone-rank shifts in Z and bound P(beta>gamma) to obtain rank stability. The random-cutoff common-shift band argument in idea_f5243b60c394 can still be valid; recheck it separately rather than discarding all of the route. No file/statement revision or theorem falsification is implied.
