---
type: search_round
title: Existing subclass exclusions leave unrestricted Gaussian geometry unresolved
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
performed_by: unknown
created_at: '2026-11-11T22:57:44.475Z'
extension_version: 0.0.4
---

## Obstructions

- The recorded marginal bound $\operatorname{FDR}\le q(|I_0|/N)H_N$ continues to exclude fixed-dimensional and bounded-null-count families. A main counterexample requires an unbounded normalized actual FDR along admissible $q$-dependent finite Gaussian models; exceeding $q$ or breaking an auxiliary inequality is insufficient.
- The nonpositive-null-covariance exclusions remain restricted to their stated regimes: independent alternative blocks, saturation with explicitly paid bad-event probability, and the draft bound $\operatorname{FDR}\le\min\{1,2e(a+1)q\}$ for $a$ arbitrary correlated alternatives. In particular, bounded $a$ and $a=O(\sqrt{\log(1/q)})$ cannot yield an unbounded normalized ratio within that null-covariance subclass. The saved observations and proofs are not duplicated.
- The recorded final-conditioning sign flip limits marginal-only use of the count tool. Its finite three-test model has an $O(q)$ actual FDR bound, so it supplies no main counterexample and no new search family this round.

## Limitations

- Main-target round 4 after helper approval produced no candidate files, no surviving counterexample, and no new mechanism or idea. All earlier records and draft observations remain unchanged.
- The search still lacks either a uniform proof or a refuting family for unrestricted null geometry containing positive covariance entries, with arbitrary rank and direction complexity and unsaturated alternatives correlated with the null vector.
- Even within nonpositive null covariance, the count bound grows with $a$; arbitrary $q$-dependent growth of correlated alternatives remains unaddressed when independence and a sufficiently small saturation error are unavailable.
- The approved conditional helper does not settle the required averaged calibration cost or the general same-actual-rank allocation. The subclass observations retain draft status; this summary supplies no native verification verdict or approval of the main theorem.
