---
type: idea
title: >-
  Conditional sign-cube free energy as an alternative to individual rank-jump
  bounds
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - sign-cube
  - conditional-rademacher
  - unproved-large-deviation-route
---

Possible analytical route for the unresolved sign-cube test cases idea_17bd1034395f and idea_bd097b4b530f. Not a proof, candidate counterexample, or new approved result. Start with the all-null full cube before the mixed-mean cap.

For d Gaussian factors, set X_j=|Z_j|, Q_d=d^-1 sum_j delta_{X_j}. Across all sign directions, T_s=d^-1/2 sum s_j X_j. Thus the exact conditional log MGF of the Rademacher signed sum is d g_Q(t), g_Q(t)=E_Q log cosh(tX). Its convex conjugate I_Q(x)=sup_t{t x-g_Q(t)} is a candidate conditional rate at a threshold sqrt(d)x. Annealed Gaussian null tail at this threshold has exponent d x²/2.

An EXACT convex-duality identity for each finite empirical Q (separate from any large-deviation approximation) is sup_x{x²/2-I_Q(x)}=sup_t{g_Q(t)-t²/2}: write x²/2=sup_t(tx-t²/2), interchange the two suprema, and use I_Q*=g_Q. The RHS is a one-parameter log-cosh free energy. Since E_{|N(0,1)|} cosh(tX)=exp(t²/2), exp(sum_j log cosh(tX_j)-d t²/2) is an exact likelihood ratio for a symmetric Gaussian mean-mixture alternative at each FIXED t.

Potential program: relate the exact simultaneous BH crossing (not merely a Chernoff upper bound) to this free energy; analyze the null probability or capped-risk expectation with a simultaneous rare empirical-magnitude deviation. This offers a statistical-mechanics/likelihood route distinct from local signed-face domination. Need uniform tail prefactors and discretization errors on the q sqrt(log1/q) scale, especially d~8log1/q, and distinguish the all-null event from the mixed-cap FDP. A pointwise conditional rate estimate or fixed-t Markov inequality cannot settle it. No claim that the displayed sup alone has the sharp constant, that a likelihood GLRT equals BH, or that signal means can realize the optimizing threshold. The constrained positive/negative mean cap destroys full sign symmetry and must be handled explicitly if extending beyond all-null.
