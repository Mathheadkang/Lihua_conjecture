---
type: search_round
title: 'Round 4: signed rank cascades and coupled clone marks'
target_asset: gaussian_bh_correlated_clone_first_variation
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_correlated_clone_first_variation_r4_s2_three_rank_coupled_marks
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:24:14.176Z'
extension_version: 0.0.4
---

## Obstructions

- Dependence of the clone marks on unchanged statistics, together with positive and negative largest-rank FDP cascades, is not by itself a violating mechanism. In the tested independent-original model with N = 3, K = 2 and means (0,1,0), exact conditional integrals retain both signs of rank-three cascades and agree with the stated minimum-mark variation. This candidate fails NOT; the conclusion concerns this tested family, not all correlated Gaussian models or all marks.
- Replacing signed FDP jumps by their positive parts, or freezing the original rejection rank before conditioning and integration, cannot establish an exact face formula: rank changes can contribute with either sign. Conditional face transport must keep both actual largest BH ranks and integrate their signed difference, including every cascade. This is a constraint on a proof strategy, not a counterexample to the target. The prospective step is registered as draft approach idea_9c14feca5024.
- Partial rejection of a perturbed group must be assessed against the positive spacing of the fixed finite expanded BH threshold grid. The candidate's exponential all-or-none estimate is consistent with the mechanism that partial rejection requires nonvanishing clone-score spread. Changing only mark parameters within already tested split families supplies no new violation mechanism; the general implication and tail estimate remain proof obligations.

## Limitations

- Round 4 has one recorded candidate, from slot 2, and no survivor. Slot 1's 123,050 finite deterministic tie checks are diagnostic support for exact-copy invariance only; they are not an exhaustive check of all deterministic scores, N, or K and do not prove copy invariance. Slot 3 supplied no new object.
- Slot 2's 60,000 numerical face checks are diagnostic only. The exact conditional-integral calculation for the recorded N = 3, K = 2 model supplies its failed-NOT outcome; finite numerical enumeration does not prove the derivative formula or rule out an untested family. This summary uses the current stage pack and the coordinating worker's round-scope report; it does not independently recheck the candidate body or rerun calculations.
- Arbitrary finite N and K, arbitrary positive-definite original covariance and allowed marks, all deterministic ties, and all largest-rank cascades still require proof. The derivative argument must control shrinking neighborhoods of intersecting original threshold faces by o(epsilon), justify truncation or domination of unbounded Gaussian marks, handle normalization terms of order epsilon squared times Z, and justify the limit and integration exchange. Probability-zero intersections alone do not suffice.
- This round establishes no uniform estimate over model parameters, no extension to singular original covariance, and no universal FDR upper bound. Singularity in the expanded exact-copy model is permitted by the target and does not relax positive definiteness of the original covariance.
