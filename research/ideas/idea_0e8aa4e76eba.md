---
type: idea
title: 反例序列必须具有无界真零方向数：后验信息的有限方向障碍
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - search-obstruction
  - bounded-directions
  - posterior-information
---

Scoped mathematical calculation checked in round5 and preserved in research/candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_three_null_directions.md; this is a search obstruction, not a native-approved theorem or an unrestricted proof. Let k be the number of distinct oriented true-null unit vectors (not the full Gaussian rank, and not the Jacobian K_t). The finite-label construction in idea_a86564a9c1fa has now been worked through independently: randomized radial marks remove the rank label, finite posterior entropy localization yields a score energy of 2 I(L;G)<=2log(k+1), and covariance factorization gives

|M| <= (F/H) sqrt{2log(k+1)(1−x)}.

The proof establishes Q Brownian innovation, absolute trace integrability and the endpoint identity before using this estimate. It handles all finite N,d, arbitrary negative true-null means, singular statistic covariance, and unrestricted false-null geometry. A true rejection requires at least one of the k standard Gaussian directional coordinates to exceed U, hence F<=kq. Since H>=3 on q<=S(3), the mixed-budget ratio is bounded above by (k/3)sqrt{2log(k+1)} for any fixed k; when 1−x=0 the trace is zero. In particular every model with at most three distinct true-null directions satisfies |M|<=2q sqrt(1−x), regardless of N, means or alternative directions.

Search consequence: varying only means, covariance angles, multiplicities, negative-mean bands, alternative complexity or Gaussian rank while keeping the number k of true-null directions bounded cannot produce an unbounded mixed-budget ratio. Any refuting sequence must have k unbounded. Rechecking fixed N=1,2,3 cases is not a new asymptotic counterexample mechanism once this derivation is accepted/reverified. The bound grows with k and therefore does not prove the desired universal estimate for k depending on q. Near-coincident but distinct directions can still have k large; no angular compression theorem has been assumed. The duplicate exact antipodal pair written at the start of round5 is preserved but explicitly contributes no new search coverage.
