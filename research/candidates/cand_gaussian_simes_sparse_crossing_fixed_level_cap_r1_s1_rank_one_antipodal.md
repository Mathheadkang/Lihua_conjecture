---
type: candidate
title: Rank-one covariance with an arbitrary sign split (all clones plus antipodes)
status: failed
target_asset: gaussian_simes_sparse_crossing_fixed_level_cap
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: e02ea4068f860cd39643c688ca2deec7a6b3a9f5aedc920fd92281c915d2d7f4
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:21:29.974Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Fix $N\ge2$, $m\in\{0,\ldots,N\}$ and $Z\sim\mathcal N(0,1)$. Put $\varepsilon_i=+1$ for $i\le m$ and $\varepsilon_i=-1$ for $i>m$, and $T_i=\varepsilon_iZ$, so $\Sigma=\varepsilon\varepsilon^{\mathsf T}$ (rank one, entries $\pm1$). Every rank-one $\Sigma\in\mathcal C_N$ has this form up to relabelling, so this candidate covers the whole rank-one boundary of $\mathcal C_N$ (the extreme degenerate case, including all-clones $m=N$ and the antipodal pair $N=2$, $m=1$). The level $q\in(0,1/4]$ is arbitrary.

## Checks

### H1

$N$ is a positive integer.

### H2

$\Sigma=\varepsilon\varepsilon^{\mathsf T}$ is symmetric, $x^{\mathsf T}\Sigma x=(\varepsilon^{\mathsf T}x)^2\ge0$, and $\Sigma_{ii}=\varepsilon_i^2=1$. Singular matrices are admitted.

### H3

Any $q\in(0,q_S]$ with $q_S\le1/4$.

### NOT

Let $K=\max\{k\le N: qk/N<\overline\Phi(u_q+1)\}$ (if no such $k$, $S_q=\emptyset$). The p-values take only two values: $\overline\Phi(Z)$ on the $m$ coordinates with $\varepsilon_i=1$ and $\overline\Phi(-Z)$ on the other $N-m$. A crossing at a sparse $k\le K$ needs at least $k$ p-values $\le qk/N<\overline\Phi(u_q+1)<1/2$; since $\overline\Phi(Z)$ and $\overline\Phi(-Z)$ cannot both be below $1/2$, the count is $m$ or $N-m$, and the best admissible rank is $k_+=\min(m,K)$, resp. $k_-=\min(N-m,K)$. Hence
$$
S_q=\{\overline\Phi(Z)\le qk_+/N\}\cup\{\overline\Phi(-Z)\le qk_-/N\},\qquad
\mathbb P(S_q)\le \frac{q(k_++k_-)}{N}\le\frac{2qK}{N}<2\overline\Phi(u_q+1).
$$
For $q\le1/4$, $u_q\ge0.674$ and $2\overline\Phi(u_q+1)\le2\overline\Phi(1.674)<0.095$. So $\mathbb P(S_q)<0.095$ uniformly in $N$, $m$, and $q\le1/4$; the conclusion holds with any $\eta\le0.9$.

## Failure

NOT fails: on a rank-one covariance only one sign class can cross, at a single threshold, so $\mathbb P(S_q)<2\overline\Phi(u_q+1)<0.095$.
