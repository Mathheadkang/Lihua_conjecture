---
type: search_round
title: Round 3 upward-jump and negative-null signed calibrations
target_asset: gaussian_bh_finite_signed_p_path_identity
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_finite_signed_p_path_identity_r3_s1_comonotone_upward_jump
  - cand_gaussian_bh_finite_signed_p_path_identity_r3_s2_upward_shifted_null
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:34:33.411Z'
extension_version: 0.0.4
---

## Obstructions

- A genuine upward jump of $A_i$ does not refute an identity that retains both signs of the net jump correction. The tested completely positively correlated heterogeneous-null constructions, including the shifted true-null case, supply a negative signed correction of $-1/4$. This correction makes the exact label-1 contribution agree with direct rejection integration; the other label agrees through its weighted baseline. The exact label contributions give total FDR $q/2$. Both recorded round-3 candidates therefore fail NOT. These are calibrations of the tested constructions, not exclusions of every comonotone or shifted-null model.
- Replacing the signed sum by its positive part would erase the negative correction in these objects and lose the exact calibration. The positive-part expression in the target is an upper bound only. Thus an attack that discards upward jumps concerns a different equality from the stated target; true upward jumps must remain distinct from removable isolated point values.

## Limitations

Neither recorded candidate survives. The additional exploration of extreme negative-null weights and endpoint events produced no plausible counterexample; it does not establish a general exclusion of those mechanisms.

The round does not prove the identity. Joint measurability, measurable finite event selection, arbitrary simultaneous crossings and constant threshold ties, endpoint limits and derivative assertions in every admissible model, conditional change of variables, and absolute integrability of the random signed jump sums still require general proofs. No quantitative bound on the positive jump budget, and no proof or refutation of the main universal-constant FDR bound, is established.

The negative signed corrections calibrate a mechanism already explicit in the target. They supply no genuinely new proof step warranting a separate approach idea.
