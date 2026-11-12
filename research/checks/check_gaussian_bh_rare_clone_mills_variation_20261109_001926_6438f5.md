---
type: falsification_check
title: 'Falsification check: gaussian_bh_rare_clone_mills_variation'
target_asset: gaussian_bh_rare_clone_mills_variation
outcome: no_counterexample_found
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:19:26.036Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_rare_clone_mills_variation_r1_s1_scalar_zero_mean failed — NOT fails: the scalar zero-mean boundary satisfies all four conclusions, with iterated derivative $-\phi(1)\{1-m(1)\}$.
- Round 1, small_cases: cand_gaussian_bh_rare_clone_mills_variation_r1_s2_scalar_null_endpoint failed — NOT fails: the scalar zero-null model retains the actual common crossing and gives exactly the proposed derivative; fractional ranks and the endpoint create no counterexample.
- Round 2, known_counterexamples: cand_gaussian_bh_rare_clone_mills_variation_r2_s1_negative_correlation_all_null failed — NOT fails: this positive-definite negatively correlated two-null model satisfies the population limit, both nonzero face coefficients, normalization and cost conclusions; mixed labels and larger models remain unchecked here.
- Round 2, extremal: cand_gaussian_bh_rare_clone_mills_variation_r2_s2_unbalanced_false_group failed — NOT fails: in this fixed unbalanced mixed-label model, the actual common-crossing finite-copy limit exists, the fractional FDP correction is second order, and the signed inverse-Mills derivative and both parameter-measure cost bounds agree with the target.
- Round 2, idea_9604780f9209: cand_gaussian_bh_rare_clone_mills_variation_r2_s3_independent_mixed_fractional failed — NOT fails: the independent two-coordinate mixed-label object has the actual finite-copy limit and signed derivative asserted by the target, with its mixed fractional FDP and alternative-atom clipping contributing only $O(\varepsilon^2)$ beyond the two face shifts.
- Round 4, idea_f372a8a1dd2f: cand_gaussian_bh_rare_clone_mills_variation_r4_s1_correlated_three_group_settled failed — NOT fails: the exact fixed correlated three-group mixed-label object has the actual finite-copy/common-largest-crossing limit, all normalization/label/cost conclusions, and the asserted signed inverse-Mills variation with an $O(\varepsilon^2)$ expectation remainder.
- Round 4, small_cases: cand_gaussian_bh_rare_clone_mills_variation_r4_s3_correlated_mixed_false_selection failed — NOT fails: this fixed positively correlated mixed-label model satisfies the actual common-largest-crossing limit and the signed derivative; correlated conditional face weights and a sign-changing terminal jump do not create an extra first-order fractional-FDP term in this case.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: The tested scalar zero-mean true-null boundary does not refute the target: both recorded candidates pass H1--H7 and fail NOT. Their actual finite-copy limit and scalar population derivative agree with the proposed variation, reported as $-\phi(1)\{1-m(1)\}$ for the displayed scalar instance. The fractional crossing and terminal endpoint in this checked scalar setting therefore do not supply a counterexample. Slots 1 and 2 cover the same family; their duplicate calculations are retained as corroboration, not counted as distinct search coverage. This obstruction is restricted to the checked scalar cases and does not rule out all scalar parameters or larger models.
- Obstruction: The tested positive-definite negatively correlated two-coordinate all-null model fails NOT: its actual population limit and both nonzero signed face coefficients agree with the proposed variation, as do normalization and the parameter-measure costs; this excludes only the checked instance, not all negatively correlated models.
- Obstruction: The tested independent two-coordinate model with means $(4,-4)$ and the selected false-null coordinate fails NOT: its actual common-largest-crossing finite-copy limit and signed variation agree with the target, with the mixed fractional FDP correction of order $O(\varepsilon^2)$ in this fixed case.
- Obstruction: The tested independent two-coordinate model with means $(0,1)$ and the selected zero-mean true-null coordinate fails NOT: the actual common crossing retains the original null label, and mixed fractional FDP plus alternative-atom clipping contribute only $O(\varepsilon^2)$ beyond the two face shifts in this fixed case.
- Obstruction: Coupled-limit and near-singular sequences that vary the original covariance, means, dimension, or other original data with the clone or perturbation limit do not refute this fixed-data assertion. Every admissible original covariance must remain positive definite and fixed throughout the stated iterated limits. This excludes the proposed coupled-limit route as a counterexample route; it does not establish the limit for any general fixed model or a bound uniform near singularity.
- Obstruction: In the all-alternative label family, sufficiently small downward offsets preserve every false-null label, so every finite-array FDP and population FDP is zero. The original FDP and all its signed face jumps are also zero. Thus the FDR value and signed-variation comparison in this family is trivial and cannot diagnose a mixed-label fractional-FDP failure. This observation does not prove the population crossing representation or its other pathwise claims.
- Obstruction: Correlation together with three mixed-label groups does not by itself produce a counterexample: the specific fixed three-group probe assigned from `idea_f372a8a1dd2f` passes H1--H7 and fails NOT. Its actual finite-copy/common-largest-crossing limit is now rigorously checked, and its expected FDP has the asserted signed inverse-Mills first variation with an $O(\varepsilon^2)$ remainder. Thus the previously numerical probe is now a failed-NOT candidate. This excludes the checked object, not every correlated three-group model or an arbitrary parameter variation of it.
- Obstruction: In the checked positively correlated two-group mixed-label model with a selected false-null coordinate, correlated conditional face weights and a sign-changing terminal jump do not produce an extra first-order fractional-FDP term. The actual common-largest-crossing limit and signed derivative agree with the target, so this candidate also passes H1--H7 and fails NOT. This obstruction concerns that checked object; positive correlation and mixed labels alone are neither a refutation nor a general proof.
- Obstruction: **Boundary and degenerate routes:** the zero-mean selected true-null boundary, fractional crossings, and terminal endpoint are already represented by the checked scalar and mixed-label cases on the board. Repeating those families supplies no new counterexample or general exclusion. Their failed-NOT conclusions remain restricted to the recorded objects; this round adds no rigorous coverage of other boundary parameters.
- Obstruction: **Small-model and label-pattern routes:** the recorded independent and correlated two-group models and the settled correlated three-group mixed-label object already test these families. Their actual common-largest-crossing limits and signed variations agree with the target in those fixed cases. The all-alternative family has identically zero FDP while its labels are preserved, so it cannot expose a mixed-label fractional-FDP discrepancy; this does not establish the population crossing claims. No new small-case candidate was produced this round.
- Obstruction: **Dropped-hypothesis and coupled-limit routes:** singular original covariance, changing original means, covariance or dimension during the limits, or replacing the required iterated limits by a coupled limit violates the fixed-data hypotheses. Such examples cannot refute this statement. Changing the actual labels, signed face measures, or common-largest-crossing rule likewise changes the assertion being tested.

## Limitations

Round 5 contains no candidates and no survivor. The board retains seven candidates across the preceding four rounds; this round contributes no new rigorous general coverage. Its boundary, small-case and hypothesis-edge directions either revisit prior families or leave the stated fixed-data setting. The earlier rigorous checks remain checks of their specified objects only.

For arbitrary fixed positive-definite original data, a proof must still connect the local inverse-Mills minimization to the common globally largest BH crossing; control root births, switches, ties, atom contacts and endpoint rank N; justify the finite-copy limit and passage through expectation at exceptional face intersections; and control fractional-FDP errors and signed face contributions at first order. No dimension-uniform, near-singular or other extended assertion follows from this round.

No new general proof step is established. The positive-root attainment observation is already recorded as idea_e9c6b6513eb6, so no duplicate approach idea is recorded. The search does not establish the lemma, a main FDR bound, or an optimization consequence. Failure to find a refutation is not proof.

Object search: 7 candidate(s) in 5 round(s).
