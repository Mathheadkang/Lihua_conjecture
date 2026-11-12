---
type: search_round
title: 'Round 5: mixed-label particle mass responses'
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r5_s1_mixed_zero_loading
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r5_s2_mixed_symmetric_reweight
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:23:18.370Z'
extension_version: 0.0.4
---

## Obstructions

- The reported mixed-tag zero-mean loading-change family fails NOT: its nonzero signed bulk response and conditional rank response are both retained by the asserted formula, while its rank response cancels exactly after background averaging. That cancellation supplies no missing first-order term in this family and is not a general conditional-rank cancellation identity.
- The reported distinct-kernel mixed-label symmetric-reweighting family fails NOT: its nonzero signed fixed-rank bulk derivative and complete suffix-minimum rank derivative agree with the asserted full response. Distinct conditional kernels and mixed labels therefore do not by themselves yield a violation in this tested family.

## Limitations

The round supplied two failed candidates and no surviving counterexample. The conclusions above use only the candidate failure lines in the stage pack; they do not independently verify candidate calculations or extend those calculations to arbitrary lawful directing-law mixtures, general conditional backgrounds, or general simultaneous mass and level perturbations. In particular, a cancellation after averaging over the background does not establish a conditional cancellation, and agreement with a suffix-minimum derivative in one family does not prove an envelope theorem for arbitrary competing active ranks with distinct perturbation slopes.

The general qualifier-transfer brackets for globally largest ranks, joint measurability and representative invariance, local suffix-minimum regularity, endpoint absolute continuity and rank-one recovery, uniform integrability of horizontal survival quotients, pointwise all-active-minima survival differentiation and its L1 convergence, the uniform conditional payoff bound, and the complete derivative and expectation interchanges remain uncovered by these failure lines.

Neither candidate tests actual deterministic global-maximizer comparisons, the normalized-objective variation in general, or post-perturbation canonical ordinary finite Gaussian recovery with o(epsilon) errors, lawful replacement of false-tagged zero means, and preservation of the full fractional FDP. Earlier failed families do not discharge these obligations. This round establishes neither the target nor either unrestricted main bound.
