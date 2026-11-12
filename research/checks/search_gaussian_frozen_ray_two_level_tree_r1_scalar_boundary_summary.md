---
type: search_round
title: 'Two-level frozen-ray search round 1: scalar boundary obstruction'
target_asset: gaussian_frozen_ray_two_level_tree
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_frozen_ray_two_level_tree_r1_s2_scalar_endpoint
statement_digest: 2b5422491f69603ba61bab7fad6c2642d6e692d0f1b1b9e16e8ff8d5ec9e825b
performed_by: unknown
created_at: '2026-11-11T01:00:57.494Z'
extension_version: 0.0.4
---

## Obstructions

- Every completely collapsed scalar realization, with all leaves equal to one standard normal variable, fails NOT: the reported candidate satisfies both target assertions with constants $C_{\mathrm{sh}}=1$ and $C_{\mathrm{tail}}=1/(2\sqrt\pi)$. Thus duplicating that scalar variable cannot produce a counterexample. This obstruction concerns the scalar family; it does not assert that every endpoint configuration is scalar.

## Limitations

- The round contains only one failed scalar candidate. Its calculation does not cover all configurations at $a=0$, $a=1$, $b_1=1$, or $b_2=1$. The existing endpoint-reduction observation `idea_fe88235f5b95` separately records reuse of the verified iid equal-weight theorem; it is not a second candidate or a new observation from this summary.
- No reported candidate tests the interior regime $0<a<1$ with nontrivial branching at both levels, including simultaneous changes in the common loading and within-group noise.
- A bound whose additive or tail constant depends on a fixed leaf count does not establish either required uniform assertion for arbitrary or growing $b_1,b_2$. Joint branching and threshold growth, without separated transitions, remain uncovered.
- No counterexample was found in the reported candidate. Neither a proof of the target nor a uniform sharp coefficient or maximal-tail bound follows from this round; finite-grid or Monte Carlo diagnostics cannot settle those requirements.
