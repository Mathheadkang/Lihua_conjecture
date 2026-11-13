---
type: candidate
title: 'Rank-one signed configurations (N=1, identical clones, antipodal pairs)'
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

For every $N\ge1$ and every sign vector $\varepsilon\in\{\pm1\}^N$ let $\Sigma=\varepsilon\varepsilon^{\mathsf T}$, so $T_i=\varepsilon_iZ$ with $Z\sim\mathcal N(0,1)$. This contains $N=1$, the all-clones matrix $\mathbf 1\mathbf 1^{\mathsf T}$ ($\varepsilon\equiv1$), and antipodal pairs ($N=2m$, half the signs $+1$, half $-1$). The candidate is the whole family, $N\to\infty$ allowed.

## Checks

### H1

$N$ is a positive integer. Pass.

### H2

$\Sigma=\varepsilon\varepsilon^{\mathsf T}$ is symmetric, $x^{\mathsf T}\Sigma x=(\varepsilon^{\mathsf T}x)^2\ge0$, and $\Sigma_{ii}=\varepsilon_i^2=1$; it is singular of rank one, which is admissible. Pass.

### NOT

Fails. Put $\tau_{\min}(A)=\min_K\tau_A(K)$. Since $\kappa_K\le1$ and $p\mapsto h(\overline\Phi^{-1}(p))$ is decreasing, $\tau_{\min}(A)=h(\overline\Phi^{-1}(1/A))\ge h(0)=\sqrt{2/\pi}$ for $A\ge2$.

General deterministic bound (any $\Sigma$): $X_K(t)\le\max_it_i$, so if $\max_it_i\le\tau_{\min}(A)$ then every term $\tau_A(K)(X_K(t)-\tau_A(K))\le\tau_A(K)(\tau_{\min}-\tau_A(K))\le0$, i.e. $M_A(t)\le0$.

Here $\max_iT_i\le|Z|$ (equal to $Z$ for clones). Hence for every $N$ and every sign pattern
$$
\mathbb P(M_A(T)\le0)\ge\mathbb P(|Z|\le\sqrt{2/\pi})=2\Phi(0.7979)-1\approx0.575 .
$$
So $(A,s_0,\delta_0)=(2,0,1/2)$ satisfies the conclusion for every member of the family; the conclusion does not fail.

The same argument covers every $\Sigma$ of rank $r$: writing $T=Bg$ with $g\sim\mathcal N_r(0,I)$ and unit rows of $B$, $\max_iT_i\le\|g\|$, so $\mathbb P(M_A\le0)\ge\mathbb P(\chi^2_r\le\tau_{\min}(A)^2)$. This is positive for each fixed $r$ but tends to $0$ as $r\to\infty$ with $A$ fixed, so a counterexample needs rank tending to infinity.

## Failure

NOT fails: $\max_iT_i\le|Z|$, and $M_A\le0$ whenever $\max_iT_i\le\tau_{\min}(A)$, which has probability at least $0.57$ uniformly in $N$ and the signs.
