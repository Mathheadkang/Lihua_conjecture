---
type: search_round
title: 'Round 3: opposite singular alternatives remain within the target order'
target_asset: gaussian_bh_one_sided_private_noise_floor_order
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r3_s1_opposite_singular_alternatives
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:23:46.052Z'
extension_version: 0.0.4
---

## Obstructions

- Within the tested growing-dimensional family with opposite common loadings and singular alternatives, the reported conditional density envelope and exact finite BH leave-one-out identity bound the normalized ratio FDR / {q sqrt(log(1/q))} uniformly. Thus this family passes the reported H1--H8 checks but fails NOT. The obstruction is at the target order: the supplied context does not establish a linear-in-q bound, an explicit constant, or an exclusion of arbitrary opposite-loading models. The distinct proposed proof step is saved as the draft [conditional-density envelope and finite BH leave-one-out reduction](../ideas/idea_f2fd32ebf376.md); the [endpoint and bounded-dimension reductions](../ideas/idea_d7fe1abf6391.md) and [three earlier growing-family reductions](../ideas/idea_3faef74c8989.md) remain separate rather than duplicated.

## Limitations

- Round 3 supplies one failed candidate and no survivor. This record summarizes only the current context pack and its failure line; it does not independently audit the candidate body, the density envelope, the leave-one-out argument, or the constant's precise dependencies.
- The near-zero positive alternative-mean threshold-selection heuristics mentioned in the earlier search report give neither a verified violation nor a quantified family exclusion. Free threshold selection or altered null labels cannot replace the original finite BH model.
- Arbitrary growing-dimensional null loading geometry, factor dimension, mixed private-noise levels, null proportions, and q-dependent alternatives under a single fixed positive null noise floor remain uncovered. No aggregation argument for the full class is established.
- Refuting the target requires a fixed positive noise floor and admissible q-indexed models with unbounded normalized FDR as q tends to zero. A vanishing floor, bounded dimension alone, or a changed largest-rank BH rule addresses a different question.
- Earlier endpoint, bounded-dimension, simplex, antipodal-cloud, and tied-alternative obstructions retain only their stated scopes. The separate draft concerning inequality (K) supplies no BH counterexample and no refutation of (T) or this structured target (S). General Mehler-kernel and finite-array aggregation steps remain unproved.
