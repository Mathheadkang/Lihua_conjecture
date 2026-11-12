---
type: search_round
title: One-sided Gaussian BH round 5 search limitations
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:36:35.926Z'
extension_version: 0.0.4
---

## Obstructions

- Prior exclusions only: perfectly duplicated true-null coordinates and the tested opposed unit-loading null blocks have reported exact FDR equal to q, so they do not yield divergence after normalization by q sqrt(log(1/q)). These were not newly checked this round.
- Prior exclusion only: uniformly bounded test counts satisfy FDR <= Nq and cannot yield the required normalized divergence. This does not control growing N.
- All five directions returned NONE: no new object, candidate file, or family obstruction was established. Finite-q excess, non-Gaussian dependence, and unrealized adaptive-rank proxies remain insufficient to refute the stated small-q Gaussian order bound.

## Limitations

This nonexhaustive round supplies no new calculation or proof coverage. Growing singular covariance families, mixed means, arbitrary covariance complexity, and hierarchical or many-direction configurations remain open; multiscale adaptive BH ranks still require a legal Gaussian realization and a rigorous normalized-divergence calculation. Absence of candidates yields no proof or verification verdict for the target.
