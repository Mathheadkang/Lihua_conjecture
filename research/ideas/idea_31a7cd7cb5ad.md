---
type: idea
title: >-
  Why conditioning on perpendicular Gaussian factors breaks the sharp two-sided
  crossing argument
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags: []
---

Source-based obstruction, not a counterexample to the FDR conjecture: slicing Z=yv+W gives other coordinates slopes alpha_j=a_j·v and residual variance s_j^2=1-||a_j||^2<=1-alpha_j^2, whereas the source's eq:upper-mixture assumes equality. The adjusted log-convexity step in eq:upper-tilde-kappa-integrand / eq:upper-kappa-adjusted-convex (TeX 6699–6765) uses b^2/(1-b^2)-alpha^2/(1-alpha^2)>=0; smaller residual variance may break it. Candidate explicit failure of generalized crossing lemma: deterministic slice with alpha=s=0 and mean mixture dPi(theta)=1(theta>=u_q)phi(theta)dtheta/q (mass 1/2) gives G_z(u)=p(u)/(2q) for all u>=u_q. Thus all u admissible and u=|z|/r activates both sign intervals, total length 2(1-r)u_q+o(u_q), violating the source small-coefficient crossing bound if extended naively. This slice need not have non-negligible Gaussian probability; the original unrestricted conjecture remains open. Small null norms alone do not remove the difficulty: source lower constructions use null loading r→0 after fixing q. Preserve this as an exact proof obligation rather than claiming a Gaussian refutation.
