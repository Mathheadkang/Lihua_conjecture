---
type: idea
title: The capped-envelope obstruction depends on the conditioning representation
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags: []
---

Scope clarification for idea_e3cb787bf90f: the iid Gaussian example uses the admissible but excessive conditioning representation d=m,A=I,residual0, under which per-null envelopes yield a vacuous capped expectation. The same covariance Sigma=I admits d=1,A=0,independent residuals, for which every conditional null CDF is exactly t and the envelope bound is q. Thus the example refutes a sharp bound uniform over all conditioning representations, or a naive full-Cholesky conditioning route. It does NOT rule out a theorem that optimizes the conditioning representation before applying envelopes. Such an infimum-over-representations extremal principle remains unproved. The regression rank-jump approach idea_aaa81d69e1fc avoids this artificial representation dependence and still has an unresolved Gaussian jump-control lemma.
