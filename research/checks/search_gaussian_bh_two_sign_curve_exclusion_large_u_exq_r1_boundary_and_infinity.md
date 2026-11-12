---
type: search_round
title: Round 1 boundary and infinite-quarter observations for large-U EX-Q
target_asset: gaussian_bh_two_sign_curve_exclusion_large_u_exq
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 422a8915f80d37bc2594b42629202589fe6eb5d11efe2e43269d21df06b3e719
performed_by: unknown
created_at: '2026-11-06T22:01:19.626Z'
extension_version: 0.0.4
---

## Obstructions

- The U=1 boundary has K=0 and [L,U]={1}; tracked sets have zero Lebesgue measure and no later points can occur.
- Empty mates cannot produce a tracked point: the large-carrier count is zero while D*(R)>=J>0.
- Infinite-B cases, including N=1 with a tracked point, do not refute the conclusions: (a) has no later points, and the TILT support is contained in [max{L,rU-K},U], of length at most ell. Thus the two tracked measures sum to at most 2ell, the right side of (b) when B is infinite. The interval [L,U] alone does not give this bound for every r.

## Limitations

No concrete candidate files or survivors were reported. These boundary and infinity observations are already recorded as the draft approach [Boundary and infinite-quarter cases for the proposed large-U EX-Q reproof](../ideas/idea_e1601340f964.md), not an independent proof verdict. This summary did not independently recompute candidate bodies, and the search is nonexhaustive. Finite-B reflected carrier transport and the measure argument remain unproved by this record; neither the proposed repair nor the source claim is declared proved or refuted.
