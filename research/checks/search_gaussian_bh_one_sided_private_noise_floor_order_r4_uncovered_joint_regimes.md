---
type: search_round
title: 'Round 4: no candidates and uncovered joint regimes'
target_asset: gaussian_bh_one_sided_private_noise_floor_order
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:26:20.656Z'
extension_version: 0.0.4
---

## Obstructions

- No new family obstruction was established in round 4: the supplied context lists no candidates. The search report's unsuccessful exploration of negative null means, vanishing null proportions, and heterogeneous private noise supplies neither a verified counterexample nor a quantified exclusion of those families. Previously recorded obstructions retain their stated scopes.

## Limitations

- This summary uses only the stage context pack. No candidate calculations or earlier obstruction arguments were independently audited, and this round supplies no survivor or new quantified exclusion.
- Growing total and factor dimensions, arbitrary null loading geometry, heterogeneous null private-noise levels bounded below by a single fixed positive floor, negative null means, vanishing null proportions, and q-dependent alternative means and dependence remain uncovered jointly. The unsuccessful searches do not exclude their separate or combined regimes.
- Near-zero alternative-mean threshold-selection heuristics still lack a complete admissible finite BH calculation. Neither free threshold selection nor relabeling nulls resolves this gap.
- The general Mehler-kernel and finite-array aggregation steps remain unproved. A counterexample would need admissible q-indexed finite models at one fixed positive null noise floor with unbounded FDR divided by q sqrt(log(1/q)) as q tends to zero; changing the floor or the largest-rank BH rule does not test this statement.
