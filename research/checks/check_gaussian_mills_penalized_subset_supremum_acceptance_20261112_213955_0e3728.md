---
type: falsification_check
title: 'Falsification check: gaussian_mills_penalized_subset_supremum_acceptance'
target_asset: gaussian_mills_penalized_subset_supremum_acceptance
outcome: no_counterexample_found
statement_digest: d3f1947df037516732eca7aa1a62191594e52c4d36ea06fed769788d4ec0bb33
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:39:55.145Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_mills_penalized_subset_supremum_acceptance_r1_s1_independent_coordinates failed — NOT fails: Simes acceptance at level $1/A$ forces $M_A<0$ by a Riemann-sum bound, and for independent (or nonnegatively correlated) Gaussians that acceptance has probability at least $1-1/A$.
- Round 1, boundary_degenerate: cand_gaussian_mills_penalized_subset_supremum_acceptance_r1_s1_rank_one_signed_clones failed — NOT fails: $\max_iT_i\le|Z|$, and $M_A\le0$ whenever $\max_iT_i\le\tau_{\min}(A)$, which has probability at least $0.57$ uniformly in $N$ and the signs.
- Round 1, boundary_degenerate: cand_gaussian_mills_penalized_subset_supremum_acceptance_r1_s1_simplex_negative_equicorrelation failed — NOT fails: the simplex is a codimension-one projection of i.i.d. coordinates, so it inherits the Simes acceptance event at level $4/A$ up to an $O(N^{-1/2})$ shift that the margin $\tau_A-\tau_{A/4}\gtrsim(\log N)^{-1/2}$ absorbs.
- Obstruction: Bounded maximum: for every $\Sigma$, $M_A\le0$ on $\{\max_iT_i\le\tau_{\min}(A)\}$ with $\tau_{\min}(A)=h(\overline\Phi^{-1}(1/A))\ge\sqrt{2/\pi}$, and $M_A\le m^2/4$ on $\{\max_iT_i\le m\}$. So every family of bounded rank (rank $r$ gives $\mathbb P(M_A\le0)\ge\mathbb P(\chi^2_r\le\tau_{\min}^2)$), in particular clones, antipodal pairs and signed rank-one patterns, fails NOT. So does every family of bounded $N$ (take $s_0=m^2/4$ with $N\overline\Phi(m)$ small). A counterexample needs $N\to\infty$, rank $\to\infty$ and $\max_iT_i\to\infty$ in probability.
- Obstruction: Simes-acceptance reduction (deterministic): if the one-sided Simes test at level $1/A$ accepts ($t_{(j)}<\overline\Phi^{-1}(j/(NA))$ for all $j$), then the Riemann-sum bound $\sum_{j\le k}\overline\Phi^{-1}(j/(NA))\le NA\,\phi(\overline\Phi^{-1}(k/(NA)))=k\tau_A(K)$ gives $M_A<0$. So every $\Sigma$ whose Simes rejection probability at level $1/A$ is at most $1-\delta_0$ fails NOT: independent coordinates (exactly $1/A$) and every $\Sigma$ with nonnegative off-diagonal entries ([lib_chi2024_positive_gaussian_simes](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md)). A counterexample must make the Gaussian Simes test at the fixed level $1/A$ reject with probability $\to1$, for every fixed $A$. That requires genuinely negative correlations.
- Obstruction: Low-codimension projections of i.i.d. coordinates: the simplex frame $T=c(g-\bar g\mathbf 1)$ (equicorrelation $-1/(N-1)$, the PSD boundary) inherits the Simes acceptance event of $g$ at level $4/A$. The $O(N^{-1/2})$ shift is absorbed by the margin $\tau_A-\tau_{A/4}\ge\log4/(z+2)\gtrsim(\log N)^{-1/2}$. Spread weak negative correlation of total size $O(1)$ in this sense therefore cannot refute.
- Obstruction: Single-scale convexity: for each fixed $k$, $M^{(k)}=\max_{|K|=k}\tau_A(K)(X_K-\tau_A(K))$ has $\mathbb E M^{(k)}\le\tau_k(h(\overline\Phi^{-1}(k/N))-\tau_k)<0$ for every $\Sigma$, using $\sum_{i\in K}T_i\le ku+\sum_i(T_i-u)_+$ at $\overline\Phi(u)=k/N$. Being a convex functional of a Gaussian vector, its median is at most its mean (Ehrhard), so $\mathbb P(M^{(k)}\le0)\ge1/2$. A counterexample must spread its failure over many scales $k$ on nearly disjoint events.

## Limitations

- This round tried no high-rank, genuinely negatively correlated construction: Hadamard or signed frames of growing rank, multiscale block designs aiming at nearly disjoint failures at about $\log N$ scales, or Gaussian analogues of Hommel-type Simes violations.
- No one checked how large the Gaussian Simes failure can be under negative dependence (the negative-dependence results of the chi2024_negative_dependence source were not consulted). That is the decisive question after the Simes-acceptance reduction.
- The low-codimension obstruction is proved only for the simplex, not for a projection out of a general fixed number of directions.

Object search: 3 candidate(s) in 1 round(s).
