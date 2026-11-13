---
type: search_round
title: >-
  Refute search round 1 for the Mills-normalized penalized subset reduction
  (boundary and degenerate cases)
target_asset: gaussian_simes_mills_penalized_subset_reduction
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_mills_penalized_subset_reduction_r1_s1_all_tied_rank_n_largest_q
  - >-
    cand_gaussian_simes_mills_penalized_subset_reduction_r1_s1_huge_loading_extreme_tail
  - >-
    cand_gaussian_simes_mills_penalized_subset_reduction_r1_s1_single_rank_one_crossing
statement_digest: d8696dc0ee5040d69e3a44c44fe818131df421b54610842f2b5ca99f0ec56f89
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:31:15.606Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every vector with a crossing at rank $k$ fails NOT through the subset $K$ of $k$ coordinates with $t_i\ge u:=\overline\Phi^{-1}(qk/N)$ (these exist, ties included, because $\overline\Phi$ is strictly decreasing). With $z=z_K$, $\tau=h(z)$, $d=u-z$ and $L=\log(1/(Aq))\ge1$, one has $\int_z^u h=\log(\overline\Phi(z)/\overline\Phi(u))=L$ exactly, independent of $k$ and $N$. Since $0<h'=h(h-\mathrm{id})<1$, $\tau(X_K-\tau)\ge\tau d-h'(z)>\tau d-1$ and $L\le\tau d+d^2/2$; with $\tau\ge h(0)=\sqrt{2/\pi}$ this forces $\tau d\ge\tfrac12\sqrt L$ whenever $L\ge0.39$. So other coordinates, ties, rank $1$ versus rank $N$, the value of $N$, and equality at the threshold cannot matter: the bound depends only on $(z_K,L)$.
- A numerical scan of $g(z,L)=h(z)(u-h(z))-(\tfrac12\sqrt L-1)$ over $z\in[0,32]$, $L\in[1,1000]$ gives minimum about $0.5005$, at $L=1$, $z\to\infty$. The extreme case $A\to\infty$, $q=e^{-1}/A$ has margin about $0.5$, so the stated constant $-1$ leaves a slack of about $1/2$ in the worst case. No parameter choice in the allowed range comes close to violating the conclusion.
- The boundary $q=e^{-1}/A$ makes the right side $-1/2$, while the singleton or full-set term is positive because $u>z_K$; at that boundary the conclusion is strictly weaker than $M_A(t)>0$.

## Limitations

- Only one worker covered the boundary/degenerate direction; no other direction (for example, a crossing whose coordinates are spread over several ranks, or the regime $q\to0$ with $N\to\infty$ jointly) was searched separately, although the obstruction above does not depend on those choices.
- Exhaustive subset maxima were computed only for $N\le5$; for larger $N$ only the lower bound through the crossing subset was evaluated, which is all the conclusion needs.
- The scan of $g(z,L)$ is on a grid, backed by the analytic argument in the first obstruction, not by a certified interval computation.
