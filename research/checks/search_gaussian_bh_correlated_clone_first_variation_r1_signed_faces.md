---
type: search_round
title: 'Clone first variation round 1: minimum marks and signed face cancellation'
target_asset: gaussian_bh_correlated_clone_first_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_correlated_clone_first_variation_r1_s1_antipodal_null_marks
  - >-
    cand_gaussian_bh_correlated_clone_first_variation_r1_s1_zero_dimensional_null
  - >-
    cand_gaussian_bh_correlated_clone_first_variation_r1_s2_mixed_labels_signed_cancellation
  - cand_gaussian_bh_correlated_clone_first_variation_r1_s2_opposite_rotations
  - cand_gaussian_bh_correlated_clone_first_variation_r1_s2_scalar_mean_split
  - >-
    cand_gaussian_bh_correlated_clone_first_variation_r1_s3_near_singular_opposed_marks
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:11:09.059Z'
extension_version: 0.0.4
---

## Obstructions

- The tested one-coordinate deterministic mean splits and opposite transverse rotations do not refute the minimum-mark formula: their actual largest-rank clone BH calculations agree with the asserted derivative, with exact local reduction or an exponentially small partial-rejection exception. The scalar mean split and opposite-rotation calculations were independently repeated across slots 1 and 2; retain both records, but count them as duplicate family coverage.
- Nonsmoothness of the minimum alone is not a counterexample mechanism: the tested antipodal transverse marks give the asserted right derivative and exponential exception bound. The tested zero-dimensional Gaussian case with unequal nonpositive drifts also satisfies all four conclusions.
- Replacing signed face jumps by their positive parts obstructs an exact derivative proof. In the tested mixed-label model, positive and negative rank-face contributions cancel exactly and the derivative is zero. A proof must assemble the signed largest-rank FDP jumps before any estimate that discards their signs.
- Approaching singularity at a fixed positive-definite covariance does not by itself refute this fixed-model statement: the tested two-coordinate all-null model at correlation 0.9999 matches the asserted derivative, including its opposed perturbation marks. The statement permits constants to depend on that covariance; this test provides no uniform estimate as correlation tends to one.

## Limitations

- All six recorded candidate attempts failed at NOT; no counterexample survived. Independent duplicates do not extend the distinct family coverage.
- The round does not prove the general finite-model identity or exhaust arbitrary N, K, means, covariance matrices, perturbation marks, deterministic ties, or multirank cascades.
- The general first-order contribution from shrinking neighborhoods of intersecting coordinate threshold faces remains to be controlled. Probability-zero intersections alone do not settle that obligation; unbounded Gaussian marks and the normalized-score remainder require justified truncation or domination.
- No uniform covariance-dependent rate, singular original-model extension, or universal FDR upper bound is established. The near-singular check concerns one fixed admissible model.
- This summary uses the native context pack's candidate outcomes and the coordinating worker's duplicate-coverage and correlation notes; it is not an independent re-verification of candidate bodies.
