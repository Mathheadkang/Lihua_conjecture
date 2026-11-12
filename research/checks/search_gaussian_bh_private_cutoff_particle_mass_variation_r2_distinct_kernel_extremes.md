---
type: search_round
title: 'Round 2: distinct-kernel extreme mass perturbations'
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r2_s1_sparse_left_tail
  - >-
    cand_gaussian_bh_private_cutoff_particle_mass_variation_r2_s2_distant_false_insertion
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:07:52.540Z'
extension_version: 0.0.4
---

## Obstructions

- Stochastically leftward contamination at fixed level fails NOT in the reported sparse-left-tail family: it raises every cutoff barrier, while a fixed interior comparison rank bounds the competing minimum and excludes escape toward rank one; the resulting full cutoff derivative agrees with the target.
- Extreme-distance false-particle insertion fails NOT in the reported distant-false-insertion family: its true-tail change is bounded by the inserted mass, and the full signed actual-rank derivative retains exactly the asserted bulk and rank terms despite the large added mean.

## Limitations

These two failed candidates test distinct-kernel extreme perturbations, not arbitrary lawful directing-law mixtures or general backgrounds. Their failure does not establish the target. Interacting mass and level changes, moving or competing suffix minima in general backgrounds, and possible failures of the qualifier-transfer brackets remain uncovered. The fixed-interior comparison argument above only excludes rank-one escape in the monotone-leftward family; it does not supply a uniform domination theorem for other perturbations.

Joint measurability and representative invariance, endpoint absolute continuity, horizontal-difference-quotient uniform integrability, the all-active-minima survival limit and its L1 convergence, the final expectation interchange, and the explicit uniform conditional payoff bound remain unverified. Actual deterministic global-maximizer comparisons and post-perturbation canonical finite competitors with errors o(epsilon) also remain unverified. No counterexample was obtained this round, and neither the target nor an unrestricted main bound is proved by these tests.
