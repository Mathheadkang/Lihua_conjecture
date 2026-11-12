---
type: search_round
title: Signed-label Stein identity round two - bivariate check and model exclusions
target_asset: gaussian_bh_signed_label_halfline_stein_identity
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r2_s1_empty_null_set
  - >-
    cand_gaussian_bh_signed_label_halfline_stein_identity_r2_s2_two_independent_nulls
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r2_s3_zero_level
  - >-
    cand_gaussian_bh_signed_label_halfline_stein_identity_r2_s4_interval_swap_copula
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:30:26.144Z'
extension_version: 0.0.4
---

## Obstructions

- Models with no original true-null labels cannot violate the null-label identities or budgets: their FDR and every signed null sum are zero, and the per-label assertions are vacuous.
- A nonzero covariance correction does not by itself refute the identity. In the tested model of two independent central nulls, the signed correction and baseline combine to the exact FDR q; this observation is limited to that checked model.
- Zero-level objects fail the strictly positive level hypothesis and do not supply the finite inverse-survival thresholds required by the statement.
- An arbitrary-dependence p-value pathology cannot refute the lemma unless its score transform is jointly Gaussian. The tested interval-swap copula fails this model hypothesis because its score difference has an atom with probability strictly between zero and one.

## Limitations

No survivor was found. The round checked an empty-null boundary and one genuinely bivariate positive-definite central-null model with nonzero correction. It did not fully check near-singular positive-definite limits, long record cascades, heterogeneous noncentral multivariate models, or the complete record-contact and score-order interface arrangement. The extremal direction produced no new plausible candidate. None of these failures proves the lemma, extends its positive-definite scope, bounds the signed below-threshold remainder, or establishes either unrestricted Gaussian BH order target. The checked elementary cancellations supply no new proof approach beyond the existing extracted derivation.
