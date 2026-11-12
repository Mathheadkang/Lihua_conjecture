---
type: search_round
title: Fixed labels and interface probes in the third Stein identity search round
target_asset: gaussian_bh_signed_label_halfline_stein_identity
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_signed_label_halfline_stein_identity_r3_s3_relabelled_auxiliary_path
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:32:05.068Z'
extension_version: 0.0.4
---

## Obstructions

- Auxiliary paths that redefine true-null membership after translation fail the fixed-original-label hypothesis. Translating a positive original mean below zero does not add that label to the original null set.
- FDR inflation alone cannot contradict this structural identity: its signed below-threshold remainder has no uniform upper bound in the statement. No new admissible inflation object with a violated identity was found.
- Large covariance row sums alone cannot contradict the asserted regularity, which is integrability within each fixed finite model, rather than a uniform bound on gradients over all covariance matrices and dimensions.
- The examined three-score tie boundary and mixed-label two-test chains did not yield a violating object. These limited probes reuse the existing coalescing and fixed-label accounting mechanisms and provide no new proof approach.

## Limitations

No survivor was found. Only the relabelled-path object was developed into a failed candidate; it failed the fixed-label hypothesis, and its later checks were left unknown. The boundary and small-case probes did not fully check heterogeneous-mean expectation identities, higher record-contact intersections, or the entire interface arrangement. Near-singular high-dimensional Gaussian expectation identities and longer record cascades remain incompletely checked. The known-counterexample and extremal directions produced no new plausible candidate. This round does not prove the lemma, extend it to singular covariance, bound the signed below-threshold remainder, or establish either unrestricted Gaussian BH order target.
