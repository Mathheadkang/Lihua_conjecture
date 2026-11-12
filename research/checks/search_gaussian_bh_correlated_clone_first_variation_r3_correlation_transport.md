---
type: search_round
title: 'Round 3: nonzero correlation transport agrees with signed BH faces'
target_asset: gaussian_bh_correlated_clone_first_variation
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_correlated_clone_first_variation_r3_s2_alternative_correlation_rotation
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:20:05.395Z'
extension_version: 0.0.4
---

## Obstructions

- Changing dependence by rotating an alternative coordinate is not by itself a violation of the signed coordinate-face formula. The round-3 slot-2 small-case candidate has N = 2 and K = 1: its exact Gaussian correlation derivative is nonzero and equals the prescribed signed face derivative. Its remaining conclusions hold pointwise or by the recorded integrable bound, so it fails NOT. This is the tested model's obstruction, not a general identity for arbitrary correlation perturbations.
- A proof cannot discard the dependence of face jumps on the unchanged coordinates merely because only one score is perturbed. The nonzero correlation-rotation check provides a calibration for a signed face-transport proof: the resulting first-order change must already be captured by the original conditional face data and actual largest-rank FDP jumps. Treating every such rotation as a zero-derivative case would miss this check.
- Earlier signed-cancellation and fixed-grid obstructions remain applicable. A proof must preserve positive and negative FDP jumps together; an expanded partial-group rejection requires a nonvanishing spread across the fixed finite threshold grid. The K = 1 check has no partial-group event and adds no new evidence for that estimate when K > 1.
- A singular original covariance, including completely coincident original threshold faces, fails the target's positive-definiteness hypothesis. Any unchecked formula-extension diagnostic there is outside this lemma and is neither an admissible counterexample nor an established counterexample to the original conjecture. Singularity of the permitted expanded clone model does not change the original-model requirement.

## Limitations

- Only one new candidate was recorded in round 3, and it failed NOT. Slots 1 and 3 produced no new plausible object. Their qualitative checks of degeneracy, labels, and hypotheses do not constitute full verification or additional exhaustive family coverage.
- This record uses the current summary pack's candidate outcome and the coordinating worker's round-scope instructions. It does not independently recheck the candidate body. The nonzero exact derivative is evidence for the tested N = 2, K = 1 model only.
- General finite N and K, arbitrary positive-definite covariance and perturbation marks, deterministic ties, and largest-rank cascades still require proof. In particular, a derivative argument must bound shrinking neighborhoods of intersecting original faces by o(epsilon) after a justified truncation, handle unbounded Gaussian marks, and remove the normalized-score remainder. Probability-zero intersections alone do not establish this limit.
- No uniform estimate over model parameters, singular-original-covariance extension, or universal FDR upper bound follows. The separately registered coincident-face extension risk remains unchecked and outside the present target.
