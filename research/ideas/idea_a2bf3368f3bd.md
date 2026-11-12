---
type: idea
title: 'Cold Phase I: rank-sensitive Gaussian geometry and extremal rank localization'
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - cold-phase-I
  - proof-architecture
  - rank-localization
  - unproved
---

Phase I cold-context proposal. Only the original Gaussian/BH problem supplied by the researcher was used. No project history or auxiliary nodes were read. This is an unproved architecture, not a result.

Goal and exact scope. First address one-sided p_i=S(theta_i+<a_i,Z>) with theta_i<=0 for true nulls, arbitrary finite N, unit vectors a_i in R^d, arbitrary other means, and nonstrict ordinary BH. Then separately address two-sided p_i=2S(|theta_i+<a_i,Z>|) with theta_i=0 for true nulls. Singular covariance is represented directly by its rank d; no regularization is assumed. The final bound must hold for the fresh supremum at every sufficiently small q.

Mechanism: rank-sensitive Gaussian geometry followed by localization of the extremal model. Gaussian measure in a fixed Euclidean dimension has radial and angular structure that an arbitrary copula lacks. First prove a bound proportional to sqrt(d), using radial coarea and the unit lengths of all a_i. Then show that a model responsible for more FDR than the desired order can be replaced by a model whose Gaussian rank is at most a constant times log(1/q), retaining a fixed positive fraction of its FDR. This is a geometric reduction of a bad model, not preservation of every pairwise correlation by a Johnson-Lindenstrauss map.

Concrete connection to BH. Write every BH threshold as t_r=S^{-1}(qr/N) in the one-sided case, and t_r=S^{-1}(qr/(2N)) in the two-sided case. Each BH cell is cut out by inequalities involving affine Gaussian projections at these finitely many thresholds. Apply radial coarea to these cells with their actual FDP weights V/r. The intended first theorem bounds the integral of these weighted cells by C q sqrt(d). A subsequent extremal/localization theorem would replace d by at most K log(1/q).

FIRST UNPROVED GATE (rank-sensitive bound). For each s in {1,2}, do constants A_s<infinity and q_s>0 exist such that, for every integer d>=1, every finite N, every family of unit vectors a_i in R^d, every allowed mean vector and null labeling exactly as in the original problem, and every 0<q<=q_s, the actual BH FDR is at most A_s q sqrt(d)? The constants must be independent of N, all means, all vector arrangements, and covariance degeneracies. Prove this separately for s=1 and s=2; do not assume that null means can be moved to zero in the one-sided problem.

SECOND UNPROVED GATE (dimension reduction, not yet justified). If a model has FDR alpha, produce a rank at most K_s log(1/q) Gaussian model in the same original class, possibly with different finite N and means, whose FDR is at least c_s alpha. Establish this only for an extremal or near-extremal model if that is sufficient. A fixed-rank reduction with no proof of FDR preservation is not acceptable.

Quick tests. Start with d=1: enumerate the directions +1 and -1, include distinct negative true-null means, and optimize arbitrary alternative means. Integrate over the single standard Gaussian exactly by all threshold breakpoints, respecting nonstrict BH. Then test d=2 and d=3 with many directions approaching a dense circle/sphere, adverse shifted alternatives, and quadrature or importance sampling. Search for FDR/(q sqrt(d)) growing with N; such growth refutes the first gate. For the second gate, compare explicit random rank-k projected/renormalized models with originals, but count this only as a test of that candidate reduction, not a proof of localization.

Constants and obstacle. The first gate must have no test-count or direction-count factor. Localization must have K_s and c_s independent of every model and q. Combining them gives A_s sqrt(K_s)/c_s times q sqrt(log(1/q)). No covariance regularization, epsilon-net cardinality, or fixed dimension may remain. The largest risk is that high Gaussian rank is essential to the extremizer; ordinary geometric localization theorems do not automatically apply to the nonconvex, signed FDP objective.
