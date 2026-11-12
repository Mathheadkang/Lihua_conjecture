---
type: search_round
title: >-
  Round 4: unequal private variances preserve the complete signed cutoff
  response
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r4_s2_unequal_private_variances
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:59:57.201Z'
extension_version: 0.0.4
---

## Obstructions

- The checked two-component family with unequal private variances fails NOT: making the false component narrow and moving its mean while leaving the broader true component stationary still produces the complete signed true-numerator plus all-minima rank-distribution response. The supplied candidate failure line also reports explicit domination uniform in the Gaussian background. Unequal private variances, through this tested mechanism, therefore do not supply a counterexample; this statement does not cover every unequal-variance directing law or transport.

## Limitations

The round-4 candidate list supplies one failed candidate, with H1 through H7 passing and NOT failing. This record summarizes that supplied failure line, without independently checking the candidate's calculations or establishing the target. Earlier reports mention cutoff endpoints and an empty true-null set, but the round-4 list supplies no separate candidate or calculations for those cases, so they yield no additional round-4 family obstruction here.

The reported unequal-variance example does not certify exact tied global suffix minima, both one-sided responses at a tie, births of crossings, general switches of the globally largest rank, or joint mean-and-level perturbations. Numerical local-minimum diagnostics from earlier rounds remain distinct from certified global ties. The special background-uniform domination reported for this example does not establish the target's domination for arbitrary directing laws and lawful bounded directions.

This round leaves general non-atomic directing laws, measurability and representative invariance, finite-model convergence and locally uniform microscopic control, marked representation and deterministic selection, continuity and attainment of the extrema, coercivity, finite endpoint recovery with errors o(epsilon), and removal of both regularizers uncovered. It does not prove the exact extremal inequalities or justify passing a derivative through any value limit.

No genuinely new proof-step obstruction follows from the supplied summary: retaining the signed numerator and every active suffix minimizer is already explicit in the target. No new approach idea is recorded.
