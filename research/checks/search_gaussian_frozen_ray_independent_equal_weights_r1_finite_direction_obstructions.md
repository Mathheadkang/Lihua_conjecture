---
type: search_round
title: >-
  Scalar and two-direction obstructions in independent equal-weight frozen-ray
  search
target_asset: gaussian_frozen_ray_independent_equal_weights
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_frozen_ray_independent_equal_weights_r1_s1_scalar_boundary
  - cand_gaussian_frozen_ray_independent_equal_weights_r1_s2_one_direction_exact
  - >-
    cand_gaussian_frozen_ray_independent_equal_weights_r1_s2_two_directions_envelope
  - >-
    cand_gaussian_frozen_ray_independent_equal_weights_r1_s3_single_coordinate_boundary
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:39:09.491Z'
extension_version: 0.0.4
---

## Obstructions

- The entire scalar family fails to refute the target, including diverging truncation and tail thresholds: for $K=1$ the full frozen-ray supremum is $\exp((Z_+)^2/2)$, and exact Gaussian integration gives the proposed truncated-moment coefficient and tail order with fixed finite constants. The three scalar candidate records therefore represent one family-level obstruction, rather than three independent mechanisms.
- The entire two-direction family also fails to refute the target: the supremum of the average is bounded by the average of the two scalar suprema. Applying scalar truncation bounds at $2c$ preserves the coefficient $1/\sqrt\pi$ up to a finite additive constant, and a union bound for the two scalar tails supplies the required tail order. Both constants can be chosen uniformly over $c,\alpha\geq2$ for this fixed dimension.

## Limitations

The round covered $K=1$ and $K=2$. It did not cover dimensions growing without bound, joint growth of $K,c,\alpha$, or the regimes in which multiple coordinates contribute at a common maximizing $w$. No worker established constants uniform over all positive integers $K$. Extending the coordinate envelope directly incurs a truncation level $Kc$ and a tail union factor $K$, so these finite-dimensional obstructions do not prove the unrestricted independent equal-weight statement.

All four candidates failed the conclusion-violation check; there is no surviving counterexample in this round. This is a search limitation, not a proof of the target or a refutation. The scalar calculation and two-direction envelope are the same finite-case steps already represented by the candidates; this summary adds no distinct proof approach requiring a duplicate idea record. The proposed planted-SNR, Gibbs, and calibration mechanisms remain unverified, and no Gaussian BH reduction follows from this round.
