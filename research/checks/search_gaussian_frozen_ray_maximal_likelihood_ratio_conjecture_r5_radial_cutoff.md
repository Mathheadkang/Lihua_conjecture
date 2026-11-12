---
type: search_round
title: >-
  Frozen-ray search round five: radial cutoff obstruction and unresolved
  families
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:29:14.824Z'
extension_version: 0.0.4
---

## Obstructions

- The supplied round-five report contains zero candidates and establishes no new family-wide exclusion. The board's existing exclusions remain scoped to rank-one sign mixtures, at most two positive-weight coordinates, the specified rapidly decaying geometric weights, and regular polygons; its general rank-at-most-two extension concerns only the order and sharp truncated-moment assertions. These are inherited results, not new round-five checks.
- A direct extension of the ambient radial cutoff used in rank two has a proof-step obstruction. For a rank-r Gaussian representation and cutoff a=sqrt(2 log c), its tail payment is c P(||G||>a)=Gamma(r/2,log c)/Gamma(r/2). Already at rank four this equals 1+log c, which exceeds the required square-root-logarithmic scale. This is a failure of that upper-bound estimate, not a violating object or a family exclusion. A possible replacement preserving the common maximizing scale is recorded as [Replace the ambient radial cutoff in higher-rank frozen-ray mixtures](../ideas/idea_e743d428fb6f.md); the replacement estimate is unproved.

## Limitations

The fifth round produced no candidates and no verified counterexample. Near-complete-correlation, product-sign, critically negatively correlated simplex, and high-rank diffuse families remain unresolved; none is excluded by absence of a candidate. Nested and hierarchical high-rank structures and uniform control of arbitrarily late maximizing scales also remain open beyond the inherited exclusions. The supplied report gives no numerical parameter values, tested grids, dimensions, or exhaustive coverage, so none is asserted.

The rank-four tail-payment calculation concerns a proof bound only and makes no claim about the actual maximum's growth. General unequal-weight or irregular rank-two geometries remain unresolved for the maximal-tail assertion. No unrestricted conjectured assertion is proved, no implication between the sharp truncated-moment and maximal-tail assertions is claimed, and no Gaussian BH reduction is established.
