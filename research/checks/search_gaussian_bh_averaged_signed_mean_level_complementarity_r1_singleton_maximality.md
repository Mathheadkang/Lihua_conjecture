---
type: search_round
title: Singleton perturbations fail actual normalized maximality
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_averaged_signed_mean_level_complementarity_r1_s1_negative_true_atom
  - >-
    cand_gaussian_bh_averaged_signed_mean_level_complementarity_r1_s2_single_false_positive_mean
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
performed_by: unknown
created_at: '2026-11-09T08:08:29.119Z'
extension_version: 0.0.4
---

## Obstructions

- A directing population consisting of a single strictly negative true mean cannot be an actual normalized global maximum when the mean penalty is positive: moving that mean toward zero weakly increases the cutoff payoff and strictly decreases the quadratic mean penalty, with the level and regularizers fixed. The negative-true-atom candidate first fails H9 (actual normalized maximality); H10 and NOT remain unknown. This rules out that singleton family as a counterexample to maximum-specific complementarity; it does not rule out such laws from the fixed-law statements.
- A directing population consisting of a single positive false mean cannot be an actual normalized global maximum: its full-FDP cutoff payoff is zero, and reducing its positive mean strictly decreases the quadratic mean penalty without changing that payoff or the level terms. The positive-false-mean candidate first fails H8 (actual normalized maximality); H9 and NOT remain unknown. Changing the positive singleton mean alone does not remove this obstruction.

## Limitations

The round covered only the negative-true singleton and positive-false singleton directions. Neither candidate reached the conclusion-failure check, and no surviving counterexample was produced. Their first failed checks concern actual global maximality, not the validity or invalidity of the proposed gradients at those laws.

Clauses 1–3 and the total-flux identity apply to arbitrary fixed lawful finite-moment directing laws. Maximum-specific complementarity, cone matching, and nonnegative normal density require an actual canonical normalized global maximum. Failure of that extra hypothesis cannot refute those conclusions, and it leaves the general-law clauses untested.

No worker covered multitype or diffuse populations, joint measurability, uniform absolute continuity and weak compactness, support-function limits and conditional active maximization, survival integration, averaged polar separation, extension from lawful velocities to the stated cone, or the fixed-regularizer vanishing-penalty assertion. The earlier report records no endpoint-sign inconsistency; the candidate summaries supply no complete verification of the endpoint cone conventions. No new proof approach is recorded: the singleton objective improvements explain failed hypotheses without resolving the target's structural obligations or the separate extremal flux estimate.
