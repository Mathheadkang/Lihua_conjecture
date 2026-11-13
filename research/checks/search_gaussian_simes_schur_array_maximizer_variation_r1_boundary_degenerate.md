---
type: search_round
title: >-
  Refute search round 1 for the Schur-path maximizer variation budget (boundary
  and degenerate cases)
target_asset: gaussian_simes_schur_array_maximizer_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_schur_array_maximizer_variation_r1_s1_antipodal_two_clone_interior_dip
  - >-
    cand_gaussian_simes_schur_array_maximizer_variation_r1_s1_schur_fixed_point_arrays
statement_digest: f01c086658ebe5ee56008da39f09da391f92f318f7cc20925eb9bfdef2f5102a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T06:03:00.097Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- **Schur fixed points are excluded.** Every all-null array with off-diagonal entries in $\{0,1\}$ fails maximality, and so does every mixture of such arrays. This family includes the identity array, the all-ones array, clone blocks, and finite independent models with $\sigma_N\to0$. Each has $S_tP=P$, so $f$ is constant $\le q$ by part 3 and $\mathcal V_-=0$. A bivariate model with loaded correlation in $[-0.3,-0.05]$ gives $B^\sigma(q)>q$; this was checked numerically at $q=0.25,0.1,0.01,0.001$ for $\sigma\le0.2$.
- **Mixtures cannot help.** $\Phi_\sigma$ is linear in $P$, $S_t$ commutes with mixtures, and $\mathcal V_-$ is subadditive under convex combinations, since $[a+b]_+\le a_++b_+$. So the maximizer set is a convex face, and $\mathcal V_-$ at a mixed maximizer is at most the average over its components. A counterexample can be taken extreme (dissociated).
- **What a counterexample must contain.** Write $\mathcal V_-=f(0)-f(1)+\mathcal V_+$. At a maximizer $f\le f(0)=B^\sigma(q_*)$ on the whole path. So a counterexample needs, at every level $q_*\le1/4$, one of two things. Either $B^\sigma(q_*)\ge1-\delta-q_*+f(1)$, a near-total breakdown of Gaussian Simes that no boundary case produces. Or the maximizer's path has upward variation at least $1-\delta-q_*-B^\sigma(q_*)$, that is, roughly $(1-q_*)/B^\sigma(q_*)$ oscillations of amplitude at most $B^\sigma(q_*)$.
- **The equicorrelated dip is a whole-path effect, not a narrow oscillation.** idea_ed169268dd35 says population values near the identity array are small at small loading. But $S_tP$ is weakly near the identity array for some $t$ only if $P$ is. Reason: $g_t(x)\ge x^2$ on $[0,1]$, and the zero $-(1-t)/t$ of $g_t$ on the negative side can carry only mass at most $\mathbb E C_{12}^+\cdot t/(1-t)$, because exchangeable PSD arrays satisfy $\mathbb E C_{12}\ge-1/(n-1)\to0$. So the dip cannot appear mid-path at a maximizer far from independence, at least for fixed $\sigma$ by continuity.
- **Interior dips exist but are small in the degenerate cases.** The antipodal two-clone array (equality case $C_{ij}=-1$) has a path that rises to $1.027q$, dips to $0.84q$ near $t\approx0.94$, and returns to $q$; $\mathcal V_-\approx0.19q$. It is beaten by its own path point, so it is not a maximizer.

## Limitations

- Maximality (H3) cannot be certified for any explicit nontrivial array, because $B^\sigma(q)$ is unknown. The round only excluded degenerate families, either by an explicit competitor or by $\mathcal V_-$ being too small.
- Population arrays whose path functions have unbounded variation were not explored; such functions are continuous but not obviously BV. The many-oscillation scenario was not explored either.
- The near-identity argument uses continuity of $\Phi_\sigma$ at fixed $\sigma$. Its uniformity as $\sigma\to0$, which is where the equicorrelated discontinuity lives, was not established.
- The bound $B^\sigma(q)>q$ is numerical at four levels only, not proved for every $q_*\le1/4$.
- Small cases (three or more coordinates), extremal parameters, and known pathological examples were left to other directions.
