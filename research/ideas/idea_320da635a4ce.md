---
type: idea
title: >-
  Conditional binomial tail control can exclude vanishing-rank private-clone
  crossings
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_growing_clone_compensated_variation
tags: []
---

Candidate elementary endpoint argument for the inner K->infinity limit; not yet independently proved. Condition on the original finite Gaussian vector, so the chosen-clone conditional mean m is finite and its private standard deviation s is fixed in (0,1). For any a with 1<a<1/s^2, Gaussian tail asymptotics suggest p(r)=S((S^{-1}(qr/N)-m)/s) <= C_m,s r^a for sufficiently small positive r. All unchanged scores have positive p-values, so below a fixed background-dependent rank strip r<=delta no unchanged atom is selected. For an empirical crossing at chosen count l, r=l/K, conditional count is Bin(K,p(l/K)); Chernoff gives P(count>=l) <= [e K p(l/K)/l]^l <= [e C delta^{a-1}]^l. Choose delta so this base is below1. For every fixed l, K p(l/K) tends to0, while the geometric upper bound sums over all l; dominated convergence of the series should show the probability of ANY crossing with l/K<=delta tends to0. This is needed because normalized rejection mass tending to0 alone does NOT imply the FDP tends to0. It provides a route to the empirical-endpoint passage without assuming compact-interior quantile convergence suffices. Remaining work: precise uniform tail power bound, finite-copy indexing and non-strict BH thresholds, coupling with unchanged atoms, continuity of the positive largest crossing, and fractional FDP convergence. For positive-root regularity, after conditioning unchanged scores, critical values of the analytic contact curves m=u(k+nu)-s S^{-1}(nu) and roots at finitely many unchanged-atom boundaries may form a null exceptional set under the continuous residual Gaussian mean; prove this explicitly rather than assuming strict crossing everywhere.
