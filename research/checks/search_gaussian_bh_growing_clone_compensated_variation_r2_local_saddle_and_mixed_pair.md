---
type: search_round
title: 'Round 2: local saddle clipping and the independent mixed pair'
target_asset: gaussian_bh_growing_clone_compensated_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_b79422ba062c
candidates:
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r2_s2_anticorrelated_allnull
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r2_s3_independent_mixed_pair
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:57:36.262Z'
extension_version: 0.0.4
---

## Obstructions

- In the fixed strongly anticorrelated two-test all-null model checked this round, clipping the upper saddle contributes only $O(s^2)$, and the separate low fractional-entry branch has exponentially small mass. Neither term contributes at the target scale $s/t_s$. With the finite-copy population limit also checked, this model fails NOT: it reproduces the asserted compensated coefficient. This excludes the proposed clipping mechanism for that fixed model, not a class with varying covariance or parameters.
- The independent mixed-label two-test diagnostic with $\theta=(-1,+1)$, $\Sigma=I$, and $q=1/4$ also fails NOT. Its finite-copy population limit and compensated coefficient were checked with the fractional true-null numerator and both root births retained. The fractional-FDP error is $O(s^2/t_s^2)$, below the target scale, and the coefficient is $0.03608922386092275$, agreeing with the signed original-rank face formula. Thus retaining fractional null-copy mass does not itself create the proposed discrepancy in this model. The unfinished diagnostic recorded as idea_b79422ba062c is covered for this model; its node status is left unchanged.
- These calculations identify a possible local proof step: show that saddle clipping and fractional-copy contributions outside the principal displacement are negligible at scale $s/t_s$ before summing signed rank-face jumps. The displayed remainder bounds establish this step only in the two fixed models checked here; extending it requires new estimates.

## Limitations

- Slot 1 produced no new indexed pathological object and wrote no candidate. The round has two new failed candidates and no survivor.
- The checks above are scoped local calculations, not a proof of the general finite-model assertion. They provide no estimate uniform over model parameters, covariance matrices, ranks, or private-copy counts.
- General finite-copy convergence to the common largest population crossing, global selection through root births and switches, interactions among multiple ranks, and signed jump accounting remain unproved beyond the checked models. In particular these calculations do not justify exchanging the two limits.
- The previous round's statement that the independent mixed pair had only a partial fractional-FDP diagnostic is superseded for that exact model by this round's full checks. Other mixed-label and higher-dimensional models remain uncovered.
