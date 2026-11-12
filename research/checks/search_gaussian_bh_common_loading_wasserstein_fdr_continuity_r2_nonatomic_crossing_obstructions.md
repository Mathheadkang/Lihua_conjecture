---
type: search_round
title: 'Round 2: nonatomic crossing pathologies preserve the tested full FDR'
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_9491db8dc586
candidates:
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s1_nonatomic_flat_crossing
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s2_diffuse_null_fold
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s3_uniform_mean_double_contact
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:47:47.056Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested nonatomic flat-crossing family, the pathwise discontinuity occurs only at a common-score value of Gaussian probability zero. The exact full FDR converges under the specified Wasserstein perturbation, so this flat-crossing construction fails NOT.
- In the tested mixed-label diffuse-null fold family, an interior fold creates a pathwise jump, but its switching level has Gaussian probability zero. Exact Gaussian averaging of the original common-cutoff, mixed-label FDP preserves FDR continuity under the proposed perturbation, so this fold construction fails NOT.
- In the tested all-null uniform-mean double-contact family, the actual largest crossing yields the exact value $F_\pi=S(B)$, while the canonical finite approximations yield $S(B_n)$ with $B_n\to B$. Thus the double contact does not produce a discontinuity in the averaged full FDR and fails NOT; the other conclusion clauses also hold on the tested laws.

## Limitations

All three round-2 candidates passed the checked hypotheses H1--H6 and failed NOT; none survived. The tests checked the four conclusion clauses only within these concrete families, including their specified microscopic-rank and ordinary finite-model approximations. They do not establish general measurability, representative invariance, crossing attainment, the dimension- and law-uniform microscopic-rank estimate, arbitrary-law Wasserstein continuity, or arbitrary-law canonical finite approximation.

The Gaussian-null switching levels found here do not show that exceptional crossings are Gaussian-null for arbitrary parameter laws, arbitrary unit directions in a separable Hilbert space, or arbitrary competing largest crossings. General vanishing-rank and endpoint-rank behavior remain unproved. The family-specific averaging calculations are not a general proof of the target or a new general proof step.
