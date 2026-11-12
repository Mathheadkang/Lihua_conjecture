---
type: search_round
title: 'Round 5: conditional null continuity and unresolved fixed-floor aggregation'
target_asset: gaussian_bh_one_sided_private_noise_floor_order
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:28:46.836Z'
extension_version: 0.0.4
---

## Obstructions

- No new family obstruction was established in round 5: the supplied context records no candidates. The unsuccessful spherical, multiple-direction, and singular-alternative explorations establish neither a counterexample nor a quantified exclusion of those families.
- The positive null private-noise floor makes each null coordinate conditionally continuous given the common factors and the other private noises, so it supplies no conditional null atom at a fixed threshold. This is a boundary observation only: the BH threshold is data dependent, alternative coordinates may have zero private noise and singular ties, and conditional null continuity alone neither proves the target nor excludes arbitrary singular alternative blocks.
- Earlier obstructions retain their recorded scopes: full-private-noise nulls and bounded total dimension; the tested simplex, antipodal-cloud, and vanishing-mean tied-alternative families; and the tested opposite-loading singular-alternative family. The last reduction bounds the normalized ratio at the target order and does not establish a linear-in-q bound or exclude all opposite-loading models. No earlier family reduction extends to arbitrary loading geometry on the basis of this round.

## Limitations

- This record summarizes only the supplied stage context pack. No candidate or earlier obstruction calculation was independently audited, and there is no new candidate, survivor, or quantitative exclusion this round.
- Growing total and factor dimensions, arbitrary loading directions, heterogeneous null private noise above a single fixed positive floor, negative null means, vanishing null proportions, and q-dependent alternative means and dependence remain unresolved jointly. Singular alternative blocks remain allowed and are not excluded by the conditional null continuity observation.
- Threshold-selection heuristics, spherical constructions, and multiple-direction searches have not supplied a complete admissible finite largest-rank BH calculation yielding a divergent normalized FDR. Their lack of a verified survivor is not an exclusion.
- The general Mehler-kernel and finite-array aggregation steps remain unproved. A refutation requires q-indexed admissible finite models at one fixed positive null noise floor with unbounded FDR divided by q sqrt(log(1/q)) as q tends to zero. A vanishing noise floor, a modified BH rule, or a conditional continuity observation does not resolve that requirement.
