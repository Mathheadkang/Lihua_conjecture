---
type: search_round
title: One-sided Gaussian BH round 7 search limitations
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 7
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:42:43.308Z'
extension_version: 0.0.4
---

## Obstructions

- Existing exclusions remain scoped: duplicated true-null coordinates and the tested opposed unit-loading null blocks have reported FDR=q, while FDR <= Nq excludes uniformly bounded test counts. These prior calculations were not repeated this round and do not cover arbitrary growing models.
- All five main-target search directions returned NONE. No new candidate file or main-target family exclusion was established.

## Limitations

Growing singular covariance, mixed means, arbitrary covariance complexity, hierarchical or many-direction configurations, and multiscale adaptive ranks remain unexcluded. A separately reported auxiliary centered-flux obstruction concerns a failed proof route: centering negative true nulls produces a harmonic flux growing with test count. It is neither an FDR-target counterexample nor a searched-family exclusion, and the actual-mean weighted replacement remains unproved. This nonexhaustive search supplies no proof or verification verdict from the absence of candidates.
