---
type: idea
title: >-
  Stress-test any per-null sharp charge using an anti-correlated alternative
  quantile grid
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - unproved_probe
  - rank_charging
  - rare_null
---

Candidate diagnostic, not a proved counterexample. Let X~N(0,1), one centered null T0=X and m−1 alternatives Tj=2 y_j−X, y_j=Q^{-1}(q j/(2m)), j=1,...,m−1, so covariance is admissible rank one and all alternative means are positive. Test any proposed per-null O(q sqrt(log(1/q))/m) charge, rather than the original global conjecture. Restrict X=x to [u,2u] where u=Q^{-1}(q/2): all means are >=2u, and every BH threshold y_r>=u, so the negative alternative branch cannot re-enter there (unlike x growing arbitrarily far). For such x, write k(x)=2m Q(x)/q. Convexity of Q on positive arguments suggests that at a qualifying rank r the alternative count is <=(k(x)+r)/2, hence actual R<=k(x)+2; this and the actual largest-rank/null-rejection condition must be checked including integer endpoints. If verified, integrating phi(x)/(k(x)+2) on [u,2u], with m large enough that k(2u)>>1, would yield a single-null contribution of order q log(1/q)/m. This would obstruct a uniform per-null square-root-log budget, while remaining far below the original global q sqrt(log(1/q)) target because the null proportion is 1/m. A correct proof may therefore need to pool nulls globally. Do not extrapolate to x beyond this interval: two-sided alternatives then re-enter via their negative branch and invalidate the naive log m construction. No finite-array bound or asymptotic has yet been independently checked.
