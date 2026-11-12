---
type: search_round
title: 'Round 1: marked-set sandwiches and signed-response diagnostics'
target_asset: gaussian_bh_whole_payoff_cameron_martin_balance
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 1290e0b2b3058fd8c486827854a892092912869a544c3ce9e36d015c6eacbd8f
performed_by: unknown
created_at: '2026-11-09T19:37:11.572Z'
extension_version: 0.0.4
---

## Obstructions

- Fixed-tag bounded background shifts do not supply a marked-set violation merely by changing the true-null numerator. On the common particle/private-mark space, the coordinatewise score bounds by the backgrounds at common-factor values shifted by plus or minus the prescribed displacement preserve global BH selection order. Inclusion then bounds both selected mass and true-null mass. The fixed-boundary and zero-mean mixed-tag cases examined in slot 1 retained this sandwich; no violating object was written.
- Opposite unit loadings, with strictly positive fixed private and common smoothing parameters, did not defeat this mechanism in slot 3: the same common-factor displacement bounds every coordinate, even when the loadings have opposite signs. Mixed tags retained the marked-set sandwich in that family. This observation concerns each fixed deterministic direction and makes no assertion of one exceptional set valid simultaneously for all directions.

## Limitations

- All three slots returned no candidate. The round established neither a counterexample nor a proof of the full checkpoint. The existing marked-set/whole-payoff Lipschitz approach is already represented by `idea_80bf54398928`; these observations do not supply a genuinely new proof approach.
- Slot 2's scalar and two-atom finite-difference discrepancies, approximately 1.4e-8 and 2e-9, were short numerical diagnostics compatible with the signed response. They are not certificates of differentiation, the envelope formula, or the asserted exchanges.
- In the three-atom diagnostic, the discretization residual decreased from approximately 5.2e-4 to 5.5e-5 under refinement. The NOT check remained unknown. No object was written, and this unresolved diagnostic is neither a failed candidate nor a violation.
- The round did not establish the coherent versions and complete conditional calculus for an arbitrary directing law, compact localization of all active minima, endpoint domination and signed-integral exchanges, or almost-everywhere ordinary differentiation and Gaussian integration by parts. No generic proof, numerical certificate, simultaneous-in-direction version claim, or uniform-q payment follows from these searches.
