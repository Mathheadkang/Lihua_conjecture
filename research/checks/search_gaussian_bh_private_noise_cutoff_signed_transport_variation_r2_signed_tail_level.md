---
type: search_round
title: >-
  Round 2: signed response under mixture competition, heavy tails, and level
  descent
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s1_competing_mixture_minima
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s2_pareto_false_tail
  - >-
    cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r2_s3_maxlevel_zero_direction
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:50:30.424Z'
extension_version: 0.0.4
---

## Obstructions

- The tested two-atom common-loading mixture mechanism fails NOT: direct integration over the combined Gaussian common displacement reproduces both the full payoff variation and the all-minima rank-distribution term; the supplied report does not certify an exact global tie.
- The checked Pareto false-mean-tail family fails NOT: a positive actual rank at every finite common-noise value does not violate the microscopic bound, since the true Gaussian numerator obeys that bound with an additional factor of one half.
- The checked pure-level-descent family at the highest allowed level fails NOT: zero mean velocity leaves a nonzero signed level response, exactly as retained by the all-minima formula.

## Limitations

All three round-2 candidates failed NOT according to the supplied failure lines. This summary uses those lines and the supplied earlier report; it does not independently verify candidate calculations or prove the target lemma. Numerical local-minimum diagnostics in the mixture example are not verified globally minimizing ties, so no obstruction is claimed for every competing-minimum family. Exact tied global suffix minima, births of crossings, and general changes of the globally largest rank remain uncovered.

The round tested pure level descent but not general joint mean-and-level perturbations or both one-sided responses at a certified tie. A finite-second-moment heavy-tailed example does not establish domination for arbitrary directing laws. Non-atomic directing laws, measurability and representative invariance, marked representation and deterministic selection, attainment and coercivity, general finite endpoint approximation, locally uniform microscopic control, and removal of both regularizers remain unverified.

No genuinely new proof-step approach is established by the supplied summaries: preservation of the true-numerator term, all active suffix minima, and the level term is already required explicitly by the target. No new approach idea is recorded.
