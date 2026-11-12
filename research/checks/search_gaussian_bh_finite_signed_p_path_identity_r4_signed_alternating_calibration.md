---
type: search_round
title: Round 4 empty-null and alternating signed-jump calibrations
target_asset: gaussian_bh_finite_signed_p_path_identity
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_finite_signed_p_path_identity_r4_s1_empty_true_null_set
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r4_s2_bidirectional_three_coordinate
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r4_s3_mixed_label_alternating_jumps
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:59:13.114Z'
extension_version: 0.0.4
---

## Obstructions

- An empty original true-null set cannot refute the per-null identity or its FDR reduction: every per-null assertion is vacuous, and the original FDR and both terms of the upper bound are exactly zero. The boundary-degenerate candidate passes H1–H6 and fails NOT.
- Opposite signs among actual net jumps do not themselves invalidate a formula retaining both signs. In the tested bidirectional three-coordinate construction, two opposite jumps give the exact signed corrections for both original null labels, matching direct integration and total FDR $11/100$. The candidate passes H1–H6 and fails NOT; this calibration does not exclude all mixed-sign models.
- Alternation of actual jumps with mixed original labels does not by itself break the identity when the full original path and labels are retained. In the tested mixed-label construction, all four alternating true jumps reproduce the selected-null contribution $F_1\approx0.0952301679$, and the other original null satisfies its weighted identity. The candidate passes H1–H6 and fails NOT; the calculation does not exclude every alternating-jump construction.

## Limitations

All three round-4 candidates fail NOT; none survives. These exact finite calibrations do not prove the identity. Joint measurability, measurable finite event selection, arbitrary simultaneous crossings and constant threshold ties, general endpoint and derivative assertions, conditional change of variables, and absolute integrability of the random signed jump sums still require general proofs.

The tested original null labels agree separately; they do not justify dropping coordinates, changing labels, replacing the exact signed sum by its positive part, or counting isolated point discrepancies as jumps. No quantitative positive-jump budget or proof or refutation of the main universal-constant FDR bound is established.

The calibrations confirm mechanisms already explicit in the finite signed identity. They provide no genuinely new proof step beyond the existing finite-event/BV approach, so no separate approach idea is recorded.
