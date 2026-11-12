---
type: search_round
title: 'Round 2 rare Mills clone search: three checked two-coordinate families'
target_asset: gaussian_bh_rare_clone_mills_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_9604780f9209
candidates:
  - >-
    cand_gaussian_bh_rare_clone_mills_variation_r2_s1_negative_correlation_all_null
  - cand_gaussian_bh_rare_clone_mills_variation_r2_s2_unbalanced_false_group
  - >-
    cand_gaussian_bh_rare_clone_mills_variation_r2_s3_independent_mixed_fractional
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:06:04.726Z'
extension_version: 0.0.4
---

## Obstructions

- The tested positive-definite negatively correlated two-coordinate all-null model fails NOT: its actual population limit and both nonzero signed face coefficients agree with the proposed variation, as do normalization and the parameter-measure costs; this excludes only the checked instance, not all negatively correlated models.
- The tested independent two-coordinate model with means $(4,-4)$ and the selected false-null coordinate fails NOT: its actual common-largest-crossing finite-copy limit and signed variation agree with the target, with the mixed fractional FDP correction of order $O(\varepsilon^2)$ in this fixed case.
- The tested independent two-coordinate model with means $(0,1)$ and the selected zero-mean true-null coordinate fails NOT: the actual common crossing retains the original null label, and mixed fractional FDP plus alternative-atom clipping contribute only $O(\varepsilon^2)$ beyond the two face shifts in this fixed case.

## Limitations

This summary uses the stage pack and the three reported round-2 candidate verdicts; it does not independently reconstruct their calculations. All three candidates pass H1--H7 and fail NOT; there is no survivor. The duplicate scalar checks from round 1 do not enlarge round-2 coverage. No statement about all members of any tested family is established.

Mixed-label coverage consists only of the two independent models displayed above. General mixed means, correlated mixed-label models, arbitrary positive-definite covariance, and larger $N$ remain unchecked. The reported $O(\varepsilon^2)$ fractional corrections are restricted to these checked mixed cases and do not establish a general error bound.

A general finite-copy-to-population proof remains open, including the atom at zero, exact background atoms, non-strict BH inequalities, endpoint rank $N$, small positive fractional ranks and their denominators, root births, root switches, ties, and exceptional face intersections. The inverse-Mills contact minimization still needs a proof connecting it to the single globally largest BH crossing and to signed face cancellation. Normalization, labels, quantile conventions, comparison costs, passage through expectation, and the claimed derivative for every fixed admissible original model are not proved by these checks. No main FDR bound follows from this round.
