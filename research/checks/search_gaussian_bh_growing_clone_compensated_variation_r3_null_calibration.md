---
type: search_round
title: 'Round 3: empty-null and independent uniform-null block cancellation'
target_asset: gaussian_bh_growing_clone_compensated_variation
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_growing_clone_compensated_variation_r3_s1_empty_null_set
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r3_s2_uniform_null_blocks
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:06:56.853Z'
extension_version: 0.0.4
---

## Obstructions

- Empty-null-set models cannot violate the compensated coefficient through an FDP contribution: the actual numerator is identically zero at every finite copy count and in the population functional, and every signed original-rank face measure vanishes. The checked three-test all-alternative case also satisfies the common-crossing equality, so it fails NOT rather than furnishing a counterexample to either assertion. This degeneracy does not establish the population-crossing assertion in general empty-null models.
- Independent uniform-null block calibration blocks the proposed discrepancy in the checked fixed model $N=3$, $\Sigma=I_3$, $\theta=(1,0,0)$, $q=1/4$, with the alternative chosen for cloning. The exact null-block leave-out identity keeps finite-copy and population FDR equal to $2q/3=1/6$ despite splitting that alternative. All integrated signed original-rank face masses vanish, so both sides of the compensated variation are zero. This is a scoped cancellation benchmark; it is not a general multirank argument.
- Changing the original mean vector or covariance with $\varepsilon$ does not test the stated fixed-model assertion. Such a parameter-dependent family fails the fixed-original-model hypothesis before its asymptotic discrepancy can establish NOT. Slot 3 supplied no new admissible object and no candidate file.
- A possible proof step is to use exact independent uniform-null block leave-out calibration before estimating clone displacements, retaining signed FDP contributions so cancellations remain visible. This step is established only for the checked independent model; its potential use is recorded as draft approach [Exact uniform-null block cancellation benchmark](../ideas/idea_e9193d1bab60.md).

## Limitations

- This round produced two new failed candidates, both failing NOT, and no survivor. The empty-null case is a zero-FDP consistency check; the three-test independent case tests alternative splitting with two exact null blocks.
- The round does not establish finite-copy convergence to the common largest population crossing in general, including behavior near population endpoints, root births, root switches, and empirical small-rank tails. It supplies no uniform-in-copy-count estimate and does not justify exchanging the two limits.
- General multirank clipping, intersections of rank faces, dependent null blocks, and fractional chosen-null contributions remain open beyond the earlier specifically checked models. Vanishing integrated signed face masses in the independent example does not assert pointwise vanishing of its face jumps or bound their positive parts.
- No claim of a proved general compensated expansion, unrestricted FDR bound, singular-original-model extension, or uniform estimate over varying original models follows from these checks.
