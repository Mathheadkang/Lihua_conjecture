---
type: search_round
title: 'CM balance round 3: pure labels, cutoff edges, and finite rank birth'
target_asset: gaussian_bh_whole_payoff_cameron_martin_balance
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 1290e0b2b3058fd8c486827854a892092912869a544c3ce9e36d015c6eacbd8f
performed_by: unknown
created_at: '2026-11-09T19:43:39.088Z'
extension_version: 0.0.4
---

## Obstructions

- Pure-label directing laws do not challenge the fixed-tag composition response: when the tag is constant, the positive-rank FDP is that constant, so its translation derivative is zero. This does not generally make the complete payoff derivative zero. In the all-true case the rank contribution can remain through the derivative of the cutoff; only the all-false case has identically zero payoff. The pure-label checks supplied no violating object.
- A specified C1 cutoff that is constant on the two sides of its transition has zero derivative at both transition edges. Consequently an edge test cannot obtain a nonzero first-order cutoff contribution by assigning an incompatible derivative at either edge. Strictly positive private variance also makes the integrated score distribution strictly increasing under a common-factor shift: a positive actual rank cannot remain constant over a nontrivial common-factor interval. A proposed positive-rank plateau therefore does not provide an admissible degeneracy in this setting.
- The tested unequal-private-variance, mixed-tag two-atom model exhibited a finite rank birth near rank 0.4306. This diagnostic did not establish a failure of the complete signed response. Its reported numerical residual decreased from approximately 5.9e-5 to 1.4e-6 under refinement, so the finite birth and a coarse residual alone do not establish a nonzero limiting discrepancy.

## Limitations

- No candidate was written and no counterexample was established. The finite-birth diagnostic leaves the NOT check unknown; decreasing numerical residuals are neither a certified error bound nor a proof of the identity. The finite birth is an observed feature of the tested model, not an unknown claim.
- This round did not establish the general conditional differentiation, coherent versions, active-minimum localization, endpoint domination, survival difference-quotient convergence, complete signed-integral exchanges, almost-everywhere ordinary differentiation, or Gaussian integration by parts for arbitrary directing laws. Pure-label and cutoff-edge compatibility does not settle mixed-label or general-support cases.
- No genuinely new proof approach was obtained beyond the existing bounded-shift, marked-set and whole-payoff route represented by idea_80bf54398928, so no duplicate approach was recorded. These searches supply neither the general theorem nor a uniform-q payment, a simultaneous exceptional set for all directions, or a bound after removing cutoff and smoothing parameters.
