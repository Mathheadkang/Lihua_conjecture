---
type: search_round
title: >-
  Growing-clone compensated variation round 1 - scalar saddle and coverage
  limits
target_asset: gaussian_bh_growing_clone_compensated_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r1_s1_single_negative_null
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r1_s3_excluded_zero_mean
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r1_s3_negative_null_singleton
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:51:02.663Z'
extension_version: 0.0.4
---

## Obstructions

- The admissible single-group negative-null family does not furnish the proposed counterexample: its common-largest-crossing calculation gives the claimed compensated coefficient, including its fractional chosen-copy numerator. The two singleton records are independent calculations of this same family; they provide no additional model coverage. The scalar saddle expansion is a possible local proof step, not a proof of the general finite-model assertion.
- A chosen zero-mean endpoint fails H3 before the conclusion can be tested: the target explicitly requires a nonzero chosen mean, and positive compensation would change the original null label. This endpoint and attempts relying on that label change are outside the asserted model.

## Limitations

- No checked counterexample survived this round. The admissible checked family has N=1; this is not evidence that all N=2 or larger models satisfy the assertion.
- The N=2 mixed-label model with theta=(-1,+1), Sigma=I, and q=1/4 reached only a partial fractional-FDP diagnostic. Its small-noise asymptotic coefficient has not been checked, and it is not a candidate or a verified near-miss. The unfinished test remains recorded as idea_b79422ba062c.
- General finite-copy convergence, existence and selection of the common largest population crossing, root births and switches, multirank cascades, and signed jump accounting remain uncovered. In particular the singleton calculation does not justify exchanging limits or dropping fractional null-copy contributions.
- Slow finite-noise numerical agreement, if observed, would not prove the compensated asymptotic coefficient; the round supplies no such proof or general uniform remainder estimate.
