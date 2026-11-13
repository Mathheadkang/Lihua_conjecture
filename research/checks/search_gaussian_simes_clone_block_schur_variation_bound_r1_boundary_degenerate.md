---
type: search_round
title: >-
  Refute search round 1 (boundary and degenerate cases) for the clone-block
  Schur-square variation bound
target_asset: gaussian_simes_clone_block_schur_variation_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_clone_block_schur_variation_bound_r1_s1_antipodal_pair_plus_null_block
  - >-
    cand_gaussian_simes_clone_block_schur_variation_bound_r1_s1_antipodal_two_blocks
  - >-
    cand_gaussian_simes_clone_block_schur_variation_bound_r1_s1_singular_mercedes_three_blocks
statement_digest: 9745c7f1d8f7ae5518e033eec521fe69f3dee7d75adf2262924621d839195795
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T00:55:54.198Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Trivial instances have a constant profile, so $\mathcal V=0$: $K=1$ or $N=1$; every $\Gamma$ with entries in $\{0,1\}$ (in particular $\Gamma=I_K$ and $\Gamma=J_K$), because then $\Gamma\circ\Gamma=\Gamma$. Empty blocks only lower the effective $K$, and the bound $K^24^Kq$ increases in $K$, so they never help.
- Singular $\Gamma$ and the equality values $\Gamma_{bc}=\pm1$ produce no jumps: the Simes rejection set in block scores is a finite union of closed orthants whose boundary lies in hyperplanes $\{y_b=\text{level}\}$, which have probability zero under any law with $\mathcal N(0,1)$ marginals. $R_t^\Gamma$ depends continuously on $t$, so $f_{q,\Sigma}$ is continuous on all of $[0,1]$, endpoints included.
- The range is too small: Simes rejection forces some block p-value $\le q$, so $0\le f_{q,\Sigma}\le Kq$. A violation would need more than $K4^K$ monotone pieces.
- Every pair correlation moves monotonically along the path: $\rho_{bc}(t)=(1-t)\Gamma_{bc}+t\Gamma_{bc}^2$ is linear in $t$. By Plackett's identity each block pair contributes at most $\sum_{\text{corners }(x,y)}\int\varphi_2(x,y;\rho)\,d\rho\le\sum\overline\Phi(\max(x,y))$, and every corner level is $\ge\overline\Phi^{-1}(q)>0$, so each corner costs at most $q$. This gives $\mathcal V\le2q$ for two blocks, including the antipodal case $\Gamma_{12}=-1$, and $\mathcal V\le5q$ for an antipodal pair plus an uncorrelated block. In general it gives $\binom K2(2^K-1)^2q<K^24^Kq/2$ (recorded as idea_83407c80a0c7). So no boundary or degenerate instance can violate the bound.
- The edge cases of $q$ do not help: as $q\uparrow1/2$ the corner levels approach $0$ but stay positive, and $\mathcal V/q$ stays below $1$ in the computed cases. As $q\downarrow0$ the computed ratio $\mathcal V/q$ is stable, about $0.37$ for two equal antipodal blocks at $q=10^{-3}$.

## Limitations

- Exact rigorous bounds were derived only for $K=2$ (any block sizes, antipodal $\Gamma$) and for $K=3$ with one moving pair. The $K=3$ case where all pairs move (singular "Mercedes" $\Gamma$ with off-diagonal $-1/2$) was checked only numerically: a 21-point grid, equal block sizes $(1,1,1)$, and $q\in\{0.45,0.01\}$.
- The general corner bound in the obstructions is a sketch: it uses Plackett's identity for an indicator (via smoothing) and the $\pm1$ corner decomposition of two-dimensional staircase sections. It was not checked in full.
- Not covered: large $K$ with many distinct levels; the regime where the number of level coincidences changes with the block sizes; non-singular $\Gamma$ near the boundary of $\mathcal C_K$ other than sign matrices.
