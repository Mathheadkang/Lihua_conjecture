---
type: search_round
title: 'Circular null-direction and polygon approximation search, round 3'
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
mode: refute
round: 3
directions:
  - idea_8a445ee0b200
  - idea_bef048aab3dc
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r3_s2_circular_polygon
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:51:37.146Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested family of circular continuous true-null directions and canonical regular-polygon approximations, H1--H6 pass and NOT fails. All four conclusion clauses hold for these tested laws: the population functional is well defined with the checked measurability, representative invariance and attained positive crossings; the stated microscopic-rank control holds; the full FDR is continuous along the specified Wasserstein approximation; and the canonical polygons yield ordinary finite Gaussian BH approximations with convergent FDR, including exact replication invariance. The ranks used are the actual largest non-strict crossings, retaining all competing crossings and endpoint possibilities; they converge almost surely outside Gaussian-null conditional critical levels. Thus replacing a continuous circular direction law by these polygons supplies no counterexample.

## Limitations

Only the circular/polygon slot produced a new candidate this round, and it failed NOT; no candidate survived. The other slots produced no new candidate: the assigned mean test was already covered by previously checked families, and proposed objects outside the target's stipulated boundary or hypothesis domain are not valid counterexamples to this target.

These family-specific checks do not establish general measurability or representative invariance, positive-crossing attainment, the dimension- and law-uniform microscopic-rank estimate, arbitrary-law Wasserstein continuity, or arbitrary-law canonical finite approximation. In particular, Gaussian-null critical levels and convergence of the actual largest rank in this circular family do not prove the corresponding assertions for arbitrary parameter laws, arbitrary unit directions in a separable Hilbert space, competing crossings, vanishing positive ranks, or endpoint rank one.

Continuity of full FDR values under atomization does not transfer rare-clone derivatives, first-variation identities, Mills stationarity, or any derivative-based optimization condition. No new general proof step was established by this round, so no approach idea is recorded.
