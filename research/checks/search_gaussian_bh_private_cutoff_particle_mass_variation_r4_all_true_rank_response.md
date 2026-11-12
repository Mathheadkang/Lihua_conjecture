---
type: search_round
title: 'Round 4: all-true transfers retain the actual-rank response'
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r4_s1_all_true_rightward_zero
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r4_s2_antipodal_true_mass
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:18:55.153Z'
extension_version: 0.0.4
---

## Obstructions

- **Lawful all-true rightward insertion at the zero-mean boundary.** This reported family fails NOT: the true and total kernels coincide throughout the perturbation, so the fixed-rank true fraction stays one and its bulk derivative vanishes. The actual largest rank nevertheless responds, and its reported nonzero response agrees exactly with the asserted signed rank term. Vanishing bulk response therefore does not produce a missing-derivative counterexample in this family.
- **Antipodal true-particle mass transfer.** This reported family also fails NOT: the all-true identity again removes the fixed-rank payoff response, while the reported actual-rank response agrees with the asserted formula retaining all active suffix minima. Opposite particle loadings alone do not produce a violation in this tested family. This failure line does not establish the envelope formula for arbitrary competing minima with distinct active slopes.

## Limitations

This round contains two failed candidates, both with an all-true sector. It does not test mixed true/false populations with nonzero signed bulk response, arbitrary lawful directing-law mixtures or general conditional backgrounds, or general simultaneous mass and level perturbations. The antipodal test retains the stated all-active-minima response but does not establish a general moving-minimum envelope theorem, nor show coverage of arbitrary competing active ranks with distinct perturbation slopes.

The qualifier-transfer brackets for globally largest ranks, joint measurability and representative invariance, local suffix-minimum regularity, endpoint absolute continuity and rank-one recovery, uniform integrability of horizontal survival quotients, and the pointwise survival limit with L1 convergence remain unverified in general. So do the uniform conditional payoff bound, the complete conditional derivative and expectation interchange. The exact all-true identity f_epsilon=1 is a reduction to rank survival, not a proof of these obligations.

Neither candidate tests actual deterministic global-maximizer comparisons, the normalized-objective variation in general, or post-perturbation canonical ordinary finite Gaussian recovery with o(epsilon) errors, lawful treatment of false-tagged zero means, and preservation of the full fractional FDP. Earlier failed families do not close these gaps. No counterexample was obtained in round 4; this record establishes neither the target nor an unrestricted main bound.
