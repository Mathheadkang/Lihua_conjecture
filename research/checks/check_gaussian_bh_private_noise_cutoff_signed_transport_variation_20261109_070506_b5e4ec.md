---
type: falsification_check
title: >-
  Falsification check:
  gaussian_bh_private_noise_cutoff_signed_transport_variation
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
outcome: no_counterexample_found
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T07:05:06.195Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r1_s2_single_true_translation failed — NOT fails: exact common translation reproduces the signed cutoff derivative and satisfies its domination.
- Round 1, small_cases: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r1_s2_two_equal_centers_opposed_means failed — NOT fails: the formula retains exactly the true-numerator loss when the total-tail first variation cancels.
- Round 2, known_counterexamples: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s1_competing_mixture_minima failed — NOT fails for the tested signed-response mechanism: direct integration over the combined Gaussian common displacement yields exactly the target's full payoff term and all-minima rank-distribution term.
- Round 2, extremal: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s2_pareto_false_tail failed — NOT fails: even though the polynomial false tail forces a positive actual rank at every finite common-noise value, the true Gaussian numerator satisfies the claimed microscopic bound, with an additional factor $1/2$.
- Round 2, boundary_degenerate: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s3_maxlevel_zero_direction failed — NOT fails: pure level descent at $q=q_{\max}$ yields precisely the signed all-minima response, including a nonzero level term despite zero mean velocity.
- Round 3, idea_acdbe615ab6c: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r3_s1_antipodal_false_transport failed — NOT fails: antipodal mixed labels do produce negative payoff-density transport beyond the cutoff, but the complete signed numerator-plus-all-minima formula reproduces that contribution with uniform Gaussian-integrable domination.
- Round 3, small_cases: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r3_s3_opposed_true_directions failed — NOT fails: opposed residual centers and nonuniform transport preserve the full signed response, including its all-minima dependence, even though the positive-rank FDP is identically one.
- Round 4, small_cases: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r4_s2_unequal_private_variances failed — NOT fails: a narrow moving false component and a broad stationary true component still give exactly the full signed numerator-plus-all-minima response, with explicit domination uniform in the Gaussian background.
- Round 5, small_cases: cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r5_s2_certified_global_tie failed — NOT fails: a certified pair of separated equal global suffix minima, with a lawful joint false-mean increase and level decrease, still yields exactly the full signed all-active-minima variation formula.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: The checked single-true common-translation family fails NOT: its exact translation response agrees with the full signed cutoff derivative and its domination bound; common translation alone therefore supplies no counterexample in this family.
- Obstruction: The checked equal-center, opposed-mean mixed-label family fails NOT: cancellation of the total-tail first variation does not cancel the true-numerator variation, and the stated formula retains exactly this numerator loss.
- Obstruction: The tested two-atom common-loading mixture mechanism fails NOT: direct integration over the combined Gaussian common displacement reproduces both the full payoff variation and the all-minima rank-distribution term; the supplied report does not certify an exact global tie.
- Obstruction: The checked Pareto false-mean-tail family fails NOT: a positive actual rank at every finite common-noise value does not violate the microscopic bound, since the true Gaussian numerator obeys that bound with an additional factor of one half.
- Obstruction: The checked pure-level-descent family at the highest allowed level fails NOT: zero mean velocity leaves a nonzero signed level response, exactly as retained by the all-minima formula.
- Obstruction: The checked antipodal mixed-label false-mean-transport family fails NOT: negative payoff-density transport beyond the cutoff is preserved by the complete signed true-numerator and all-minima rank-distribution formula, with the supplied failure line reporting uniform Gaussian-integrable domination; this sign reversal alone does not contradict the target.
- Obstruction: The checked all-true antipodal family with opposed residual centers and nonuniform mean velocities fails NOT: positive-rank FDP equal to one does not eliminate cutoff/rank variation, and the supplied failure line reports agreement with the full signed response, including all-minima dependence.
- Obstruction: The checked two-component family with unequal private variances fails NOT: making the false component narrow and moving its mean while leaving the broader true component stationary still produces the complete signed true-numerator plus all-minima rank-distribution response. The supplied candidate failure line also reports explicit domination uniform in the Gaussian background. Unequal private variances, through this tested mechanism, therefore do not supply a counterexample; this statement does not cover every unequal-variance directing law or transport.
- Obstruction: The checked family with two separated equal global suffix minima and a lawful joint false-mean increase and level decrease fails NOT: the complete signed variation retains every active minimizer and reproduces the reported response, so this certified-tie mechanism supplies no counterexample in the tested family.

## Limitations

The round-5 list supplies one failed candidate with H1 through H7 passing and NOT failing. This summary records the supplied failure line; it does not independently certify the global tie or recheck the candidate calculations. Unlike the earlier numerical local-minimum diagnostics, this candidate is reported to certify two separated equal global suffix minima. That certification concerns this example and is not a verification of the target lemma.

The reported joint direction does not cover both one-sided responses at every tie, arbitrary multiplicities or continua of active minima, births of crossings, or general switches of the globally largest rank. It supplies no general domination argument for arbitrary directing laws and bounded lawful mean velocities.

General non-atomic directing laws, measurability and representative invariance, finite-model convergence and locally uniform microscopic control, marked representation and deterministic selection, continuity and attainment of extrema, coercivity, finite endpoint recovery with errors o(epsilon), and removal of both regularizers remain uncovered by this round. The exact extremal inequalities and any interchange of differentiation with value limits are not established.

No genuinely new proof-step obstruction follows from this failure line: retaining every active suffix minimizer under joint mean-and-level variation is already explicit in the target and the earlier search board. No additional approach idea is recorded.

Object search: 9 candidate(s) in 5 round(s).
