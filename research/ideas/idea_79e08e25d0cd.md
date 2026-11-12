---
type: idea
title: >-
  A legal Gaussian BH FDP tilt can have disconnected support and infinite
  Poincare constant
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_entropy_coherence_trace_budget
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - fdp-tilt
  - entropy-stability
  - poincare
  - singular-calibration
---

A source check found that generic Gaussian transport-entropy stability cannot be applied to the FDP-tilted law without checking its extra hypotheses. In the legal finite one-sided model N=2, theta=(0,0), T=(G,-G), G standard normal, and 0<q<1/2, ordinary BH has R=1 exactly when |G|>=a with a=normal-survival-inverse(q/2), and never R=2. Thus F=q and Q=Gaussian conditioned on the two separated tails. Its mean is zero and Var_Q(G)=1+a h(a)>1. It has no finite ordinary gradient Poincare constant: a smooth function equal to -1 on the negative tail and +1 on the positive tail can interpolate only inside the Q-null gap, giving positive Q variance but zero Q Dirichlet integral. This is not a counterexample to the entropy-coherence trace budget; it only rules out silently assuming covariance upper bounds or a finite Poincare constant for every legal FDP tilt. The primary-source stability theorem at arXiv:1906.05904 requires additional Poincare or covariance assumptions, so it was not added as an applicable dependency. No external theorem is needed for the finite diagnostic.
