---
type: search_round
title: >-
  Refute search round 1 for the pathwise clump-bracket BH bound (boundary and
  degenerate cases)
target_asset: bh_clump_bracket_pathwise_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - cand_bh_clump_bracket_pathwise_bound_r1_s1_all_tied_at_level
  - cand_bh_clump_bracket_pathwise_bound_r1_s1_rejected_one_unrejected_clumpmate
  - cand_bh_clump_bracket_pathwise_bound_r1_s1_staircase_collapse_full_clump
statement_digest: 505283800a561693969245cf14db866c63b7fbf613631c942f088194185139db
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:34:40.168Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every configuration fails NOT termwise: for each $i\in\mathcal R_q(p)\cap S$ one has $\Psi_i\ge 1/R$. Indeed $p^{(i,*)}\le p$ coordinatewise, so by BH monotonicity $R_{i,*}\ge R$ and the indicator $p_i\le qR/N\le qR_{i,*}/N$ holds; $Np_i/q\le R$ and $D_i\le|\mathcal R_q(p)\cap K_l|\le R$ since every $j\in K_l$ with $p_j\le p_i$ is rejected; and $R_{i,0}\le R$ because lowering an already rejected $p_i$ to $0$ leaves $\widehat k$ unchanged, and then raising the other clump members to $1$ cannot increase the BH count. All other $\Psi_j\ge0$. So no counterexample exists in any family, including ties, rank jumps, and clumps whose removal collapses the BH count (collapse makes $R_{i,0}$ smaller, which only enlarges $\Psi_i$).
- Equality is attained when each rejected member of $S$ sits on the final threshold ($p_i=qR/N$) or is the unique rejected member with all other clump members unrejected-and-indicator-killed; e.g. all p-values tied at $q$.
- Computational evidence: exhaustive exact-rational enumeration for $N\le3$, $q\in\{1/10,1/3,1/2,2/3,9/10\}$, p-values on a grid of thresholds $qk/N$, $qk/N\pm10^{-3}$, $0$, $1$, all $S$ and all partitions (122610 cases): no violation, minimum slack $0$. Random tests with $N=4$ to $7$ (30000 cases, up to three clumps): no violation.

## Limitations

- The search covered only the deterministic inequality; the expectation corollary follows from it by taking expectations and was not tested separately.
- The termwise argument above is informal (written as an obstruction, not a proof) and only shows the bound is far from tight when clumps contain several rejected members; it says nothing about whether the bound is useful downstream.
- $N\ge8$ and continuous (off-grid) p-values were not enumerated; by the termwise argument they cannot give a counterexample.
