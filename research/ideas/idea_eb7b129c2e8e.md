---
type: idea
title: The full-array ultrametric route contradicts Lei's lower bound
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_worst_case_approximate_ghirlanda_guerra
  - gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer
  - gaussian_bh_ultrametric_covariance_order_bound
tags:
  - parallel-round-20261112
  - route-3
---

UNVERIFIED agent observation, 12 Nov 2026. Lemma 2 of the full-array ultrametric route bounds W_sigma(q) by U_sigma(q), the best FDR over models whose whole covariance is a nonnegative ultrametric correlation matrix. All correlations are then nonnegative, so one-sided Gaussian p-values are PRDS (Lei 2026 states this; Benjamini-Yekutieli 2001), and with nonpositive null means BH has FDR at most q; hence U_sigma(q) <= q (see also idea_c629576ad268). Lemmas 1 and 2 together would give W_sigma(q) <= q for every sigma, and compactification item 5 would give F_1(q) <= q. But the approved Lei lower bound gives F_1(q) >= q sqrt(log(1/q))/sqrt(pi) + q/2 > q for small q. So Lemmas 1 and 2 cannot both hold, and the route as stated is inconsistent. Lei's lower family has positively correlated nulls and negative null-alternative correlations, so the obstruction is the requirement that alternatives also sit in the nonnegative tree. The null-only tree variant (route via ultrametric null trees at maximizers) does not have this defect, since its tree condition is on null-null correlations only and Lei's family can lie in its class. Checking the PRDS step for composite nulls is the only point to confirm.
