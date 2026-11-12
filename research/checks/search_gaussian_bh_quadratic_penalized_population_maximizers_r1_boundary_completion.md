---
type: search_round
title: Round 1 boundary-tag obstruction for quadratic penalized population maximizers
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r1_s1_zero_mean_mixed_tags
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:47:25.791Z'
extension_version: 0.0.4
---

## Obstructions

- Finite zero-mean mixtures with both true-null and alternative tags, including irrational mixing weights, do not obstruct canonical finite approximation. Keep true-null means at zero, move alternative-tagged zero means to positive values tending to zero, retain the unit directions, and rationalize the finitely many positive weights while preserving total mass. These tag-respecting approximants converge in $W_1$, their second moments tend to the original zero moment, and the approved fixed-loading continuity theorem gives FDR convergence. Thus this boundary family fails the counterexample check NOT; the analytic completion itself creates no contradiction in part 2.

## Limitations

- The round board records only one boundary-degenerate candidate and no surviving counterexample. Its failure does not prove the target.
- The recorded candidate does not cover unbounded mean support, general moment-controlled truncation and quantization, compactness and attainment, vanishing-penalty limits, or the full range of lawful deterministic transports and signed comparisons.
- No candidate in the board tests simultaneous endpoint approximation at an $o(\epsilon)$ rate, or all fixed-loading hypotheses needed to invoke the approved continuity theorem for general populations.
- The earlier search report also mentions minimal atomic models and escaping second-moment mass, but supplies no corresponding candidate failure lines in this pack. Those remarks are not treated as established family obstructions here; in particular, $W_1$ convergence alone does not imply second-moment convergence.
