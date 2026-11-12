---
type: search_round
title: Round 1 obstructions for slowly growing factor dimension
target_asset: slow_factor_dimension_one_sided_sharpness
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_slow_factor_dimension_one_sided_sharpness_r1_s2_antipodal_pair
  - cand_slow_factor_dimension_one_sided_sharpness_r1_s2_growing_small_family
  - >-
    cand_slow_factor_dimension_one_sided_sharpness_r1_s3_dense_saturated_budget_edge
  - cand_slow_factor_dimension_one_sided_sharpness_r1_s3_independent_full_rank
  - >-
    cand_slow_factor_dimension_one_sided_sharpness_r1_s3_negative_antipodal_nulls
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:11:49.210Z'
extension_version: 0.0.4
---

## Obstructions

The supplied round handoff reports four search directions and no survivor. The context pack lists five failed candidates from `small_cases` and `drop_hypothesis`; the other direction-level findings below come from the supplied handoff. These are summaries of reported checks, not independent certifications.

- **Too few tests cannot sustain the proposed normalization.** The reported small-family check rules out every family with $m=o(\sqrt{\log(1/q)})$: its FDR divided by $q\sqrt{\log(1/q)}$ tends to zero. The antipodal two-test example has FDR exactly $q$, and the growing negatively correlated simplex family also fails the violation check. Increasing a representation's dimension without increasing the effective small-model FDR does not overcome this obstruction.
- **Full covariance rank does not exceed a factor-dimension budget by itself.** Independent residual noise can produce a full-rank covariance matrix in an admissible one-factor representation with zero loadings. The reported independent family has vanishing normalized FDR even when its finite test count depends on $q$. Conversely, the supplied source check reports that the rank-one common-factor lower construction embeds at $d=1$ despite a positive-definite full covariance matrix, so covariance positive definiteness does not obstruct the matching lower construction.
- **The tested saturated and negative-null boundaries do not yield overshoot.** The dense saturated family near the permitted budget edge was reported to fail the violation check through the finite-level radial bound and a uniform chi-square quantile estimate. The negative antipodal null family has reported FDR at most $q$. The supplied handoff also identifies $\Gamma_0=0$ in the radial bound when all null loadings have unit norm; this boundary therefore supplies no surviving counterexample in the reported search.
- **Oscillation of an admissible budget is not itself a counterexample.** The supplied check found no violation from a nonmonotone or oscillating $D(q)$ satisfying the stated rate condition. Any putative counterexample must produce an actual FDR violation along an admissible sequence; oscillation alone neither removes the available $d=1$ lower construction nor establishes failure of the required uniform upper estimate.

## Limitations

- No survivor was supplied. Failure of these candidates does not prove the target, and this summary did not rederive their calculations or inspect their bodies.
- A general uniform quantile proof is still required for every integer $1\leq d\leq\lfloor D(q)\rfloor$ under the stated rate condition. A fixed-dimension expansion, or an estimate established only for the tested dense family, does not discharge that obligation.
- The upper assertion must still cover arbitrary finite test counts depending on $q$, all allowed mean vectors including negative one-sided null means, and all loading vectors of norm at most one, uniformly over the budget. The reported boundary checks do not independently establish this full coverage.
- The source lower-construction embedding is a supplied provenance finding, not a new source verification by this summary worker. No result about the unrestricted Gaussian upper-bound target follows from this restricted search.
