---
type: search_round
title: Round 1 family obstructions for the exact two-sided pivotal identity
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s1_singular_identical_nulls
  - >-
    cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s2_rank_one_shifted_pair
  - cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s2_singleton
  - >-
    cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s3_singular_negative_pair
  - >-
    cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s4_countermonotone_magnitudes
  - >-
    cand_gaussian_bh_two_sided_exact_pivotal_identity_r1_s5_growing_perfect_dependence
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:03:29.941Z'
extension_version: 0.0.4
---

## Obstructions

- Perfectly tied all-null Gaussian clusters, including singular covariance and arbitrarily large cluster size, do not refute the identity: the low forced-zero threshold occurs only where the numerator vanishes. The reported family has FDR exactly q and zero pivotal excess, so increasing dimension within this family does not produce a violation.
- The tested singular negatively dependent Gaussian pairs, including a shifted alternative, preserve the exact FDR decomposition even when the pivotal excess is negative. A negative excess by itself is compatible with the statement and is not a counterexample.
- Singleton models do not yield an exceptional correction: the empty residual and zero-rejection cases satisfy the reported identity.
- Countermonotone Gaussian-marginal magnitude copulas outside the jointly Gaussian class fail the joint-Gaussian hypothesis H3. They cannot refute this target regardless of any later check.

## Limitations

This record summarizes six candidate failure lines from five directions; candidate bodies were not reread and their calculations were not independently verified here. Five admissible candidates failed NOT, while the copula candidate failed H3 and its later checks remained unknown. No survivor was reported.

The round does not exhaust general full-rank or higher-rank covariance, heterogeneous null and alternative configurations, arbitrary residual-dependent Borel thresholds, or all branch endpoint and duplication configurations. The reported special families do not establish parts (a) through (f) for every admissible input. In particular, preservation of the exact identity does not prove a uniform upper bound on pivotal excess or an unrestricted FDR bound. No counterexample found is not a proof.
