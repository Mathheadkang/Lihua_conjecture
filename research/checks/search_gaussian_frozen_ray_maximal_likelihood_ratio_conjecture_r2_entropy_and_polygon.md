---
type: search_round
title: >-
  Geometric-weight and regular-polygon obstructions for the frozen-ray maximal
  likelihood ratio
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r2_s2_geometric_weight_entropy
  - >-
    cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r2_s3_regular_polygon_rank_two
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:13:00.785Z'
extension_version: 0.0.4
---

## Obstructions

- Every truncated geometric weight family
  $\omega_i=(1-r)r^{i-1}/(1-r^n)$, $n\geq3$, $0<r\leq1/9$, fails NOT for every correlation matrix, including growing rank and arbitrary maximizing scales. With $H(\omega)=-\sum_i\omega_i\log\omega_i$ and $S_\omega=\sum_i\sqrt{\omega_i}$, the coordinate envelope $\Lambda\leq\sum_i\omega_i\exp((Z_i^+)^2/2)$ combines $H(\omega)\leq H_*=-\log(8/9)+(\log9)/8$ with $S_\omega^2\leq2$. These bounds yield $\mathbb E\min(c,\Lambda)\leq\sqrt{\log c/\pi}+1+\sqrt{H_*/\pi}$ and $\mathbb P(\Lambda\geq\alpha)\leq\sqrt{2/\pi}/(\alpha\sqrt{\log\alpha})$ for all $c,\alpha\geq2$, hence also the order assertion. Small weight entropy controls the moment while square-root summability controls the tail; the two mechanisms are separate. Source: `cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r2_s2_geometric_weight_entropy`.
- Every uniformly weighted regular polygon of arbitrary size $n\geq3$, with $Z_j=\langle(\cos(2\pi j/n),\sin(2\pi j/n)),G\rangle$ and $G\sim N_2(0,I_2)$, fails NOT, despite unbounded support and entropy $\log n$. A radial split gives $\mathbb E\min(c,\Lambda)\leq\sqrt{\log c/\pi}+3/2$, hence the order assertion. Grid spacing separately gives the maximal-tail assertion with $C_{\rm tail}=256$. The moment proof extends to all rank-at-most-two Gaussian geometries with arbitrary deterministic probability weights: writing $R=\|G\|$ and $a=\sqrt{2\log c}$, split at $R=a$, use $c\mathbb P(R>a)=1$, and integrate each coordinate envelope on $|Z_i|\leq a$. This extension has been recorded as the draft proof approach `idea_6e2b553d5db5`; the tail exclusion here remains scoped to regular polygons. Source: `cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r2_s3_regular_polygon_rank_two`.

## Limitations

No candidate survived. These family calculations and the recorded proof approach are search evidence, not independently approved results, and prove none of the three unrestricted assertions. The round does cover arbitrarily large effective support and rank under strongly decaying geometric weights, and unbounded weight entropy under regular rank-two geometry. It does not exclude diffuse-weight families with unbounded covariance rank, general unequal-weight or irregular rank-two geometries for the maximal-tail assertion, or a dimension-uniform cost of arbitrarily late maximizing scales outside the covered families. A bounded entropy alone does not supply the square-root summability used in the geometric family's tail estimate. No implication between the sharp moment and maximal-tail assertions is asserted. Any independent-coordinate or product-sign diagnostics without a written family exclusion remain inconclusive.

The context pack supplied only failure summaries. Native `show` calls retrieved the two round-two candidates' `Object` and `Checks` sections because exact parameter ranges, uniform constants, the geometric weights' two distinct summability controls, and the polygon tail proof's reliance on regular spacing could not be recovered from those summaries alone. No other candidate bodies, proof plans, or target proof were read.
