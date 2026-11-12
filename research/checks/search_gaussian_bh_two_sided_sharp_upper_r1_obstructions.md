---
type: search_round
title: First-round obstructions for the unrestricted two-sided Gaussian BH bound
target_asset: gaussian_bh_two_sided_sharp_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_gaussian_bh_two_sided_sharp_upper_r1_s1_growing_singular_blocks
  - >-
    cand_gaussian_bh_two_sided_sharp_upper_r1_s1_near_rank_one_exponential_dimension
  - cand_gaussian_bh_two_sided_sharp_upper_r1_s1_rank_one_growing_dimension
  - cand_gaussian_bh_two_sided_sharp_upper_r1_s2_dense_rank_two_ring
  - cand_gaussian_bh_two_sided_sharp_upper_r1_s2_signed_finite_types
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:36:03.538Z'
extension_version: 0.0.4
---

## Obstructions

These are summaries of the five failed candidate reports, not independent certification of their calculations. No candidate survived the asymptotic NOT check.

- Exact rank-one Gaussian dependence is reported to give FDR at most q, uniformly over dimension and nonnull means; repetition alone therefore cannot produce the proposed square-root-log inflation.
- The tested near-rank-one family, with exponentially growing dimension and vanishing independent Gaussian noise, is reported to retain FDR of order q. This obstruction is specific to that perturbation regime.
- The grouped-null entropy argument is reported to exclude the tested growing singular-block family when the logarithm of the number of distinct null blocks is negligible relative to the square root of log(1/q). A bounded number of null p-value types, including the signed finite-type candidate with arbitrary multiplicities, falls in the same regime.
- The tested dense rank-two circle is reported to have FDR asymptotic to sqrt(2/(pi e)) times q. Increasing angular density in that construction does not reach the conjectured normalization.

## Limitations

- Fixed-dimensional latent Gaussian models with an interior residual-noise component, and growing-block models outside the reported entropy regime, remain unresolved. The common-factor-gated test case is also unresolved.
- The separate covariance-convexity counterexample refutes that proposed proof shortcut, not the unrestricted asymptotic bound. It supplies no successful NOT check for this target.
- The source lower construction matches the proposed leading constant; finite-q excess above an asymptotic approximation does not refute the limsup statement. Neither point proves the uniform upper bound.
- The round supplies five failed families and no survivor; it does not exhaust q-dependent dimensions, means, or singular and nonsingular correlation structures, and its candidate calculations still require any independent verification the later argument relies on.
