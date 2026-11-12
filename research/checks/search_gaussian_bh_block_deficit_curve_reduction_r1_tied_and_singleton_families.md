---
type: search_round
title: Round 1 singleton and tied families for the block deficit-curve reduction
target_asset: gaussian_bh_block_deficit_curve_reduction
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - cand_gaussian_bh_block_deficit_curve_reduction_r1_s1_singleton_unit_loading
  - cand_gaussian_bh_block_deficit_curve_reduction_r1_s3_singular_background_tie
  - cand_gaussian_bh_block_deficit_curve_reduction_r1_s4_singular_tied_rank_jump
statement_digest: f1dda2f50a23bcb44d5591faa42a4ed7c15018980386fbefca5819ed441dbef8
performed_by: unknown
created_at: '2026-11-06T21:22:53.552Z'
extension_version: 0.0.4
---

## Obstructions

- The tested singleton with unit loading does not refute the reduction: both ranks equal 1 and the central difference is zero.
- The tested singular simultaneous-background-tie and threshold-mate-tie examples do not refute the reduction: downward raw-deficit jumps preserve the largest qualifying ranks under the suffix envelope, which retains the reported unit-increment conditions.

## Limitations

Three candidates in boundary_degenerate, drop_hypothesis, and known_counterexamples failed NOT; no survivor was reported. This summary uses their supplied failure lines without independently recomputing candidate bodies. These limited families do not establish the reduction for general block models, every admissible background curve, or its deterministic-to-random consequence. The separate cold-audit observation was not examined here. No general proof or verification verdict follows from this search.
