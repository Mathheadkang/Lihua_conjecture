---
type: search_round
title: 'OU bridge round 2: full signed budget obstructions'
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r2_s1_tangent_reserve_full_fdp
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r2_s2_critical_positive_clusters
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r2_s3_redundant_latent_tetrahedron
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:03:25.616Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested tangent-reserve family, increasing the number of driver groups does not turn the approved positive-budget counterexample into a counterexample to the full signed OU bridge: the full actual-BH FDP obeys $J(f)\geq17F/120$, and the tested family's bridge ratio stays below $40$. The hole-covariance calculation is a family-specific obstruction; it does not establish the general gate or approve the existing hole-covariance idea.
- Growing-rank critical clusters with the tested nonnegative correlations cannot refute the gate: their full FDR satisfies $F\leq q\pi_0$, so the positive excess and bridge ratio vanish. Letting the within-cluster correlations approach one does not remove this obstruction.
- Adding unused Gaussian coordinates to the tested four-score, rank-three tetrahedron preserves both $F$ and the full signed budget $J(f)$. The fixed-rank hole-covariance estimate gives a uniform finite bridge ratio for this family, with $F\leq4q$; redundant latent dimension therefore cannot produce a growing-rank refutation.

## Limitations

All three round-2 candidates fail NOT. The calculations do not control arbitrary mixed-sign covariance with growing effective rank, varying means, rank switches or simultaneous ties. They neither prove a universal BH bridge nor refute it. The generic analytic estimate, the required source verification, the signed-mixture reduction beyond the checked cases and the general BH-specific quantitative gate remain proof obligations; the asserted FDR consequence remains conditional. The hole-covariance direction is already recorded as idea_9146e39dd8dd and is neither duplicated nor assigned approved status here.
