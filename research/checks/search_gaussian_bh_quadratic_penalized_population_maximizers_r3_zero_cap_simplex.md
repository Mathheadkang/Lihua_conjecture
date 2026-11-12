---
type: search_round
title: 'Round 3: zero-cap one-dimensional populations form a compact simplex'
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r3_s1_zero_cap_antipodal_directions
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:53:00.312Z'
extension_version: 0.0.4
---

## Obstructions

- In the fixed dimension-one, zero-second-moment-cap family, all mean parameters are zero, every unit direction is either +1 or -1, and the analytic completion permits both tags at zero. Thus the entire cap set consists of probability laws on four fixed tagged atoms. It is the image of the compact four-coordinate probability simplex. Matching common atom mass and transporting only unmatched mass gives Wasserstein distance at most one half the diameter of that finite set times the sum of the absolute coordinate-weight differences. Hence the simplex map is continuous in Wasserstein distance and its image is compact. Irrational weights, antipodal directions, and either tag do not produce noncompactness in this family. This explains the failed NOT check of the sole round-3 candidate; it is not a counterexample to the target.

## Limitations

- The round contains one recorded boundary-degenerate candidate. Its failure checks only the dimension-one zero-cap compactness mechanism, not the full target.
- The argument does not establish positive-cap compactness, lower semicontinuity of the second moment in general, preservation of the full tagged domain under arbitrary limits, penalized attainment, or applicability of the approved FDR continuity theorem to general maximizing sequences.
- No new recorded candidate checks general canonical approximation with convergent moments, vanishing-penalty limits, signed lawful transport comparisons, or simultaneous endpoint recovery with errors of order o(epsilon). Earlier mixed-zero and empty-null approximation obstructions are prior-round evidence only.
- Compactness across varying ambient dimensions is outside the fixed-dimension target. No law convergence as the penalty vanishes, unpenalized attained maximizer, finite-model derivative transfer, or unrestricted Gaussian BH order bound follows from this round.
