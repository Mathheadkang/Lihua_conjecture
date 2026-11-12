---
type: search_round
title: 'Round 1: rank-one and two-coordinate envelope obstructions'
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s1_rank_one_signs
  - >-
    cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s2_two_coordinates_all_correlations
  - >-
    cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s3_antithetic_zero_weight
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:05:33.659Z'
extension_version: 0.0.4
---

## Obstructions

- Every rank-one correlation model $Z_i=s_iX$, $s_i\in\{-1,1\}$, with arbitrary finite dimension and probability weights, fails NOT: after aggregating signs into $p=\sum_{s_i=1}\omega_i$, each half-line has the envelope $\Lambda\leq b e^{X^2/2}+1-b$, with $b=p$ or $1-p$. Binary entropy is at most $\log2$, so half-line Gaussian integration gives the sharp truncated-moment bound with $C_{\rm sh}=1/2+\sqrt{\log2/\pi}+1/(2\sqrt{\pi\log2})$, hence also the order bound; Mills' inequality gives $C_{\rm tail}=1/\sqrt\pi$. This includes $p=0,1$, arbitrary zero weights, and the third worker's specific antithetic object $(s,\omega)=((1,-1,1),(1/2,1/2,0))$. Sources: `cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s1_rank_one_signs` and `cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s3_antithetic_zero_weight`.
- Every $n\leq2$ model, with arbitrary weights and correlation $\rho\in[-1,1]$ (including singular endpoints), fails NOT: $\Lambda\leq\sum_i\omega_iM_i\leq\max_iM_i$, where $M_i=e^{(Z_i^+)^2/2}$. Marginal Gaussian integration and $H(\omega)\leq\log2$ give $\mathbb E\min(c,\Lambda)\leq\sqrt{\log c/\pi}+1+\sqrt{\log2/\pi}$, and a union bound gives $\mathbb P(\Lambda\geq\alpha)\leq1/(\sqrt\pi\alpha\sqrt{\log\alpha})$, uniformly for $c,\alpha\geq2$. The same conclusion holds after adding zero-weight coordinates, since these do not change $L_w$. Source: `cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r1_s2_two_coordinates_all_correlations`.

## Limitations

The round found no surviving counterexample. Its family calculations have not received independent survivor verification and do not prove any unrestricted assertion. No worker covered effective support at least three with covariance rank at least two, general growing-dimensional geometry, unbounded weight entropy, or a dimension-uniform cost for a maximizing scale appearing arbitrarily late in $w$. The coordinate envelope extends to finite support size $m$ as $\mathbb E\min(c,\Lambda)\leq1+\sqrt{(\log c+H(\omega))/\pi}$ and $\mathbb P(\Lambda\geq\alpha)\leq m/(2\sqrt\pi\alpha\sqrt{\log\alpha})$; its entropy and support factors leave precisely the required uniformity unresolved. No implication between the sharp and maximal-tail assertions is claimed.

The context pack contained only failure summaries. Native `show` calls retrieved the named candidates' `Checks` sections to determine their exact bounds and the first and third candidates' `Object` sections to scope parameters and identify the overlap; the nested `NOT` heading was not separately addressable. No other candidate bodies were read.
