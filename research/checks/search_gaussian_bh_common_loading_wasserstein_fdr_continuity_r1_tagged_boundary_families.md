---
type: search_round
title: 'Round 1: tagged boundary families preserve full FDR continuity'
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s1_mixed_zero_common_score
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s2_independent_two_block_completion
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s3_canonical_zero_tag_boundary
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s3_vanishing_extreme_alternative_mass
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:43:43.729Z'
extension_version: 0.0.4
---

## Obstructions

- Coincident zero-mean scores with a mixture of true and alternative tags do not by themselves create a discontinuity: in the tested common-score family, the full FDR is exactly the true-tagged mass times $q$. The tested strictly positive alternative shifts and rational approximations preserve convergence. This family satisfies the checked hypotheses and fails NOT.
- The tested independent two-block completion also preserves the full mixed-label functional: its FDR is exactly $qw$, and canonical rational finite arrays converge to the completed value $q/2$. Thus this explicit independent-block family fails NOT; independence of these blocks supplies no counterexample.
- In the tested family with vanishing alternative mass and diverging alternative means, the FDR difference is $q\varepsilon_n\to0$, and microscopic ranks reject only alternatives. This escape of alternative means does not produce a nonvanishing FDR discrepancy in that family, so NOT fails.
- A sequence that changes the canonical tag across zero fails the stipulated Wasserstein-convergence hypothesis: changing a tag costs one unit in the parameter metric. For the tested canonical-zero-boundary candidate the first failure is H6, and NOT remains unknown. A mean approaching zero alone cannot establish convergence when its tag changes with nonvanishing mass.

## Limitations

The round checked concrete atomic families only. It did not prove the asserted continuity for arbitrary nonatomic parameter laws, or settle how competing largest crossings behave under arbitrary Wasserstein perturbations. The independent two-block calculation and the coincident-score calculation are restricted examples, not a general proof step. The vanishing-mass example does not establish the uniform microscopic-rank estimate over all laws. General measurability, attainment, representative invariance, arbitrary-law finite approximation, and the endpoint and vanishing-rank assertions remain unproved by these tests. No candidate survived, and no general proof of the target follows from this round.
