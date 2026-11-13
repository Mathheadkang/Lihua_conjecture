---
type: candidate
title: >-
  Independent coordinates with N tending to infinity (and all nonnegative
  correlations)
status: failed
target_asset: gaussian_mills_penalized_subset_supremum_acceptance
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: d3f1947df037516732eca7aa1a62191594e52c4d36ea06fed769788d4ec0bb33
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:39:54.654Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$\Sigma=I_N$ for every $N\ge1$, so $T_1,\dots,T_N$ are i.i.d. $\mathcal N(0,1)$; the family is $N\to\infty$. The check also covers every $\Sigma\in\mathcal C_N$ with $\Sigma_{ij}\ge0$ for all $i\ne j$.

## Checks

### H1

Pass.

### H2

$I_N$ is symmetric positive definite with unit diagonal. Pass.

### NOT

Fails, with $s_0=0$ and $\delta_0=1-1/A$, for every $A\ge2$.

Deterministic reduction (any $t\in\mathbb R^N$). Let $t_{(1)}\ge\dots\ge t_{(N)}$ and write $z_p=\overline\Phi^{-1}(p)$. Suppose the Simes test at level $\alpha=1/A$ accepts, i.e. $t_{(j)}<z_{j/(NA)}$ for every $j$ (equivalently the one-sided p-values satisfy $p_{(j)}>j\alpha/N$). Because $u\mapsto\overline\Phi^{-1}(u)$ is decreasing,
$$
z_{j/(NA)}\le NA\int_{(j-1)/(NA)}^{j/(NA)}\overline\Phi^{-1}(u)\,du,
$$
and the substitution $u=\overline\Phi(x)$ gives $\int_0^p\overline\Phi^{-1}(u)\,du=\int_{z_p}^\infty x\phi(x)\,dx=\phi(z_p)$. Hence for $|K|=k$,
$$
\sum_{i\in K}t_i\le\sum_{j\le k}t_{(j)}<NA\,\phi(z_{k/(NA)})=k\,\frac{\phi(z_{\kappa_K/A})}{\kappa_K/A}=k\,\tau_A(K).
$$
So $X_K(t)<\tau_A(K)$ for every $K$, and $M_A(t)<0$.

Probability. For i.i.d. continuous p-values the Simes identity gives $\mathbb P(\exists j:p_{(j)}\le j\alpha/N)=\alpha$ exactly. So $\mathbb P(M_A(T)<0)\ge1-1/A\ge1/2$ for every $N$.

Nonnegative correlations. By the Chi-Ramdas-Wang inequality [lib_chi2024_positive_gaussian_simes](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md), the Simes rejection probability at level $\alpha$ is at most $\alpha$ whenever $\Sigma_{ij}\ge0$ for $i\ne j$. The same reduction then gives $\mathbb P(M_A\le0)\ge1-1/A$ for all such $\Sigma$, singular ones included.

## Failure

NOT fails: Simes acceptance at level $1/A$ forces $M_A<0$ by a Riemann-sum bound, and for independent (or nonnegatively correlated) Gaussians that acceptance has probability at least $1-1/A$.
