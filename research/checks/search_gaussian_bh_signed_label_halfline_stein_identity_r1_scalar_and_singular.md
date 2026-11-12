---
type: search_round
title: Scalar and singular-boundary checks of the signed-label Stein identity
target_asset: gaussian_bh_signed_label_halfline_stein_identity
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r1_s1_single_boundary
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r1_s2_single_null
  - >-
    cand_gaussian_bh_signed_label_halfline_stein_identity_r1_s3_singular_duplicate
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r1_s4_antithetic_pair
  - >-
    cand_gaussian_bh_signed_label_halfline_stein_identity_r1_s5_deep_negative_null
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:42.988Z'
extension_version: 0.0.4
---

## Obstructions

- Single-test true-null models do not violate the conclusion: the only edge has trigger equal to its label, so the covariance correction is zero and the exact false discovery rate equals its baseline. The tested central-null boundary saturates the baseline budget, while the tested deeply negative null remains below it.
- Exact duplicate and exact antithetic Gaussian pairs fail the positive-definiteness hypothesis: their covariance matrices have a zero eigenvalue. They cannot refute the stated positive-definite lemma; later checks were not performed on those objects.

## Limitations

No surviving candidate was found. The completed admissible examples were scalar, so this round did not test a genuinely multivariate positive-definite model with nonzero covariance corrections, a long record cascade, or all record-contact and score-order interfaces. The singular examples give no conclusion about positive-definite approximations. These failures do not prove the lemma, extend it to singular covariance, bound the below-threshold remainder, or establish either unrestricted Gaussian BH order target. The scalar cancellation is already part of the extracted derivation and yields no new proof approach to record.
