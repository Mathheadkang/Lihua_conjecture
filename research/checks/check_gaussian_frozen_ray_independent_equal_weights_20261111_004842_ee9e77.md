---
type: falsification_check
title: 'Falsification check: gaussian_frozen_ray_independent_equal_weights'
target_asset: gaussian_frozen_ray_independent_equal_weights
outcome: no_counterexample_found
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:48:42.590Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_frozen_ray_independent_equal_weights_r1_s1_scalar_boundary failed — NOT fails: the entire scalar boundary family satisfies both conclusions with dimension-independent constants, while attaining their leading moment coefficient and tail order.
- Round 1, small_cases: cand_gaussian_frozen_ray_independent_equal_weights_r1_s2_one_direction_exact failed — NOT fails: exact integration verifies both proposed inequalities for the whole $K=1$ family.
- Round 1, small_cases: cand_gaussian_frozen_ray_independent_equal_weights_r1_s2_two_directions_envelope failed — NOT fails: both the sharp-coefficient moment bound and the required tail order hold uniformly in $c,\alpha$ for $K=2$.
- Round 1, drop_hypothesis: cand_gaussian_frozen_ray_independent_equal_weights_r1_s3_single_coordinate_boundary failed — NOT fails: the complete $K=1$ family obeys both inequalities with fixed finite constants, even as the truncation and tail thresholds diverge.
- Round 2, boundary_degenerate: cand_gaussian_frozen_ray_independent_equal_weights_r2_s3_late_onset_growing_dimension failed — NOT fails: at $K=n\geq3$ and $c=\alpha=e^{n^2}$, the moment excess is bounded by $2$ and the normalized tail by $5$, uniformly in $n$.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: The entire scalar family fails to refute the target, including diverging truncation and tail thresholds: for $K=1$ the full frozen-ray supremum is $\exp((Z_+)^2/2)$, and exact Gaussian integration gives the proposed truncated-moment coefficient and tail order with fixed finite constants. The three scalar candidate records therefore represent one family-level obstruction, rather than three independent mechanisms.
- Obstruction: The entire two-direction family also fails to refute the target: the supremum of the average is bounded by the average of the two scalar suprema. Applying scalar truncation bounds at $2c$ preserves the coefficient $1/\sqrt\pi$ up to a finite additive constant, and a union bound for the two scalar tails supplies the required tail order. Both constants can be chosen uniformly over $c,\alpha\geq2$ for this fixed dimension.
- Obstruction: The growing family indexed by every integer n >= 3 with K=n and c=alpha=exp(n^2) fails to refute either assertion: the candidate report bounds the truncated-moment excess above sqrt(log(c)/pi) by 2 and the normalized tail alpha sqrt(log(alpha)) P(Lambda >= alpha) by 5, uniformly in n. This rules out this entire specified sequence of delayed extreme thresholds, rather than just individual numerical parameter choices. It does not rule out other joint growth rates of K, c, and alpha. The reported mechanism combines scalar coordinate envelopes and clipping/variance control; the supplied summary does not contain the candidate's detailed derivation.
- Obstruction: No new family-level obstruction was established this round. Fixed small-dimension repetitions add no exclusion beyond the existing scalar-envelope arguments; examples with dependent coordinates or unequal weights do not satisfy the target hypotheses and cannot refute this independent equal-weight statement.
- Obstruction: No new family-level obstruction was established in round 4, and no candidates were recorded. The existing scalar, two-direction, and specified delayed-threshold exclusions retain only the scope stated on the search board.
- Obstruction: A fixed dimension or a fixed truncation or tail threshold, without a sequence forcing the required constants to diverge, cannot refute the existence of universal finite constants. Repeated fixed-parameter boundary checks therefore provide no new refutation mechanism.
- Obstruction: Objects obtained by dropping coordinate independence or equal weighting violate the target hypotheses; they cannot refute this independent equal-weight statement.
- Obstruction: No new family-level obstruction was established in round 5, and no candidates were recorded. The existing scalar, two-direction, and specified delayed-threshold exclusions retain exactly the scope stated on the supplied search board. This round adds no quantitative exclusion or proof mechanism.

## Limitations

No new checked object was obtained this round. The critical collective-SNR regime, simultaneous contributions at a common maximizing parameter, and general joint growth of dimension and thresholds remain unresolved. Fixed-parameter checks cannot establish divergence of the required universal constants; dropping independence or equal weighting leaves the target hypotheses.

The critical-truncation route remains unverified. Neither target assertion, the sharp truncated-moment coefficient, nor constants uniform over all dimensions and thresholds follow from this search. No Gaussian BH reduction follows. No new counterexample was established; absence of one is not a proof. No duplicate approach idea was recorded.

Object search: 5 candidate(s) in 5 round(s).
