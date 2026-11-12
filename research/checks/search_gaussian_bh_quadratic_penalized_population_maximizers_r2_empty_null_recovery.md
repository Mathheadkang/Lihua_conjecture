---
type: search_round
title: 'Round 2: empty-null unbounded means permit canonical moment recovery'
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r2_s3_empty_null_unbounded_means
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:50:19.532Z'
extension_version: 0.0.4
---

## Obstructions

- Empty true-null mass cannot itself obstruct canonical finite approximation, even with unbounded positive mean support and finite second moment. All labels can remain alternative labels. Truncate positive means above a finite threshold and quantize them to strictly positive values; quantize unit directions on the compact sphere. The mean error tends to zero in second mean by the finite second-moment tail bound, so the resulting finite laws have convergent first and second mean moments. Rationalize their finitely many positive weights with total mass preserved, choosing the weight errors small relative to the largest retained mean and its square. This preserves Wasserstein and second-moment convergence. Every endpoint and approximant has FDP identically zero because its true-null mass is zero; hence its FDR is exactly zero, regardless of competing BH crossings. This entire empty-null family fails the counterexample check NOT. The round's single recorded candidate supplies this obstruction; it supplies no counterexample.

## Limitations

- Only one boundary-degenerate candidate is recorded for this round. Its failure does not prove the target or the general approximation claim.
- The empty-null obstruction does not address mixed labels, alternative-tagged zero boundary points, or the fixed-loading continuity hypotheses needed for nonzero FDR. The earlier mixed-zero obstruction remains prior-round information, rather than new evidence from this round.
- No recorded candidate this round checks compactness and attainment, maximizing-sequence moment bounds, vanishing-penalty limits, general lawful transports and their signed comparisons, or simultaneous endpoint approximation with errors of order o(epsilon).
- Fixed finite dimension is a hypothesis of the target. Cross-dimensional noncompactness is outside its stated scope and is not a counterexample. The reports about minimal atomic models and escaping second-moment mass have no corresponding new candidate failure lines in this pack and do not establish additional family obstructions here. In particular, Wasserstein convergence alone does not imply second-moment convergence.
