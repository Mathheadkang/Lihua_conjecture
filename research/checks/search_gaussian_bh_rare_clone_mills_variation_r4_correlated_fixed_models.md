---
type: search_round
title: Fixed correlated mixed-label probes agree with rare Mills variation
target_asset: gaussian_bh_rare_clone_mills_variation
mode: refute
round: 4
directions:
  - idea_f372a8a1dd2f
  - boundary_degenerate
  - small_cases
candidates:
  - >-
    cand_gaussian_bh_rare_clone_mills_variation_r4_s1_correlated_three_group_settled
  - >-
    cand_gaussian_bh_rare_clone_mills_variation_r4_s3_correlated_mixed_false_selection
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:16:47.907Z'
extension_version: 0.0.4
---

## Obstructions

- Correlation together with three mixed-label groups does not by itself produce a counterexample: the specific fixed three-group probe assigned from `idea_f372a8a1dd2f` passes H1--H7 and fails NOT. Its actual finite-copy/common-largest-crossing limit is now rigorously checked, and its expected FDP has the asserted signed inverse-Mills first variation with an $O(\varepsilon^2)$ remainder. Thus the previously numerical probe is now a failed-NOT candidate. This excludes the checked object, not every correlated three-group model or an arbitrary parameter variation of it.
- In the checked positively correlated two-group mixed-label model with a selected false-null coordinate, correlated conditional face weights and a sign-changing terminal jump do not produce an extra first-order fractional-FDP term. The actual common-largest-crossing limit and signed derivative agree with the target, so this candidate also passes H1--H7 and fails NOT. This obstruction concerns that checked object; positive correlation and mixed labels alone are neither a refutation nor a general proof.

## Limitations

Round 4 contains two failed-NOT candidates and no survivor. The supplied board reports seven candidates across four rounds. The round-3 limitations quoted in the context pack are historical: their claim that the three-group probe is numerical only is superseded by its round-4 finite-copy limit and rigorous expectation-remainder check.

Neither checked object supplies a proof for arbitrary fixed positive-definite original data. A general argument must still connect the local inverse-Mills minimization to the common globally largest BH crossing, control all root births, switches and ties together with atom contacts and endpoint rank $N$, justify passage through expectation and exceptional face intersections, and bound fractional-FDP errors and signed face contributions at first order. The concrete $O(\varepsilon^2)$ remainder does not provide a uniform estimate over other models, near-singular covariances or increasing dimensions.

The positive-root attainment observation is already recorded as `idea_e9c6b6513eb6`; it is not duplicated here. The supplied candidate failure lines establish no additional general proof step warranting a new approach idea. No general lemma, singular-covariance extension, main FDR bound, or optimization consequence is established by this round.
