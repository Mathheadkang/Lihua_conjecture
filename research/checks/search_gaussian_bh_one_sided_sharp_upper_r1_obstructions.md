---
type: search_round
title: 'One-sided Gaussian BH upper-bound search: round 1 obstructions'
target_asset: gaussian_bh_one_sided_sharp_upper
mode: refute
round: 1
directions:
  - idea_9692ea16c23a
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_one_sided_sharp_upper_r1_s1_weak_common_gate_quantiles
  - >-
    cand_gaussian_bh_one_sided_sharp_upper_r1_s2_antipodal_negative_null_boundary
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:05:04.945Z'
extension_version: 0.0.4
---

## Obstructions

- **Rank-one covariance cannot attain the proposed scale.** Every admissible rank-one unit-diagonal Gaussian covariance has a representation $T_i=\theta_i+s_iZ$ with $s_i\in\{-1,1\}$. A false rejection at level $q<1/2$ requires $s_iZ\geq\overline\Phi^{-1}(q)$, because its mean is nonpositive and its BH threshold is at most $q$. Thus any false discovery lies in two Gaussian tails of total probability $2q$, and $\operatorname{FDR}\leq2q$ uniformly over dimension, signs, and means, including negative true-null means and arbitrary alternative means. The antipodal tied-block subfamily in [the boundary candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r1_s2_antipodal_negative_null_boundary.md) has the stronger exact bound $\operatorname{FDR}\leq q$. Both bounds vanish after division by $q\sqrt{\log(1/q)}$.

- **The prescribed common-gate source-quantile family crosses too early to violate the bound.** This obstruction concerns [the weak-common-gate candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r1_s1_weak_common_gate_quantiles.md), with $B=\lceil q^{-1}\rceil$, $\alpha=q/B$, $k=\lceil\alpha^{-2}\rceil$, null loading $r=1/k$, gate loading $\epsilon=(\log(1/q))^{-1/2}$, block size $m=k^{k^3}$, and the retained source secondary means discretized by midpoint quantiles. A single block's secondary nonnulls force a global BH crossing and cap the rejection cutoff; the same cap holds after setting any null p-value to zero. Averaging two block gates supplies a Gaussian cap whose correlation with the null block's factor stays uniformly below one. The resulting conditional null-tail envelope is integrable, and the discarded factor events cost $o(q)$, giving $\operatorname{FDR}=O(q)$ for these exact finite arrays. The candidate includes null means $0$ and $-q$; the conditional tail bound also dominates more negative means whenever the same nonnull-only cap is preserved. This family therefore has zero ratio on the proposed scale.

## Limitations

- The rank-one obstruction does **not** cover a model with one common factor plus independent residuals: a covariance of the form $aa^{\mathsf T}+\operatorname{diag}(1-a_i^2)$ generally has rank greater than one, and false discoveries need not be confined to two tails of one scalar factor.
- The common-gate obstruction is tied to the stated loading schedule, retained source secondary means, and sufficiently fine prescribed quantile arrays. The round gives no uniform $O(q)$ bound for arbitrary null loadings $r$, other joint $q,B,r,\epsilon$ regimes, arbitrary finite block sizes or discretizations, or modified secondary populations that evade the nonnull-only crossing cap.
- Unrestricted higher-rank dependence, arbitrary growing dimensions, and heterogeneous negative true-null means coupled to general alternative configurations remain uncovered outside the two families above. No reduction of those models to either searched family was established.
- Neither failed candidate proves the unrestricted upper bound or its proposed constant $1/\sqrt\pi$. No asymptotic counterexample survived this round, and the sharp uniform target remains open.
