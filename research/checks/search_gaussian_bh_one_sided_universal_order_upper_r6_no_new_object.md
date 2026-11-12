---
type: search_round
title: One-sided Gaussian BH round 6 search limitations
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 6
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:39:06.474Z'
extension_version: 0.0.4
---

## Obstructions

- Prior calculations exclude the perfectly duplicated true-null family and tested opposed unit-loading null blocks: their reported FDR equals q. The bounded-N union bound FDR <= Nq excludes uniformly bounded test counts. These scoped exclusions were not newly checked and do not cover arbitrary growing models.
- No new family exclusion was established: all five directions returned NONE, with no new object or candidate file.

## Limitations

The round adds no new calculation or proof coverage. Arbitrary growing singular covariance, mixed means, hierarchical or many-direction models, and multiscale adaptive BH ranks remain unexcluded; no admissible Gaussian family with rigorously computed normalized divergence was supplied. Absence of candidates does not prove or verify the universal order upper bound.
