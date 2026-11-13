---
type: candidate
title: >-
  Simplex frame (extreme negative equicorrelation) and random low-dimensional
  frames
status: failed
target_asset: gaussian_simes_schur_variation_few_block_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: ae49babfdb545830e8ad7375a17d918e1fb1ba20e49b625bd07dbdd7738fee3a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:45:35.188Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

(a) Simplex frame: $\Sigma=\frac{N}{N-1}I-\frac1{N-1}J$, the boundary case $\rho=-1/(N-1)$ of equicorrelation (singular, rank $N-1$, $Z$ sums to zero; $N$ distinct directions). Then $\Sigma\circ\Sigma$ is equicorrelated with $\rho=1/(N-1)^2$ and $R(t)$ is equicorrelated with
$$
\rho(t)=-(1-t)/(N-1)+t/(N-1)^2 ,
$$
realized as $Z=a\varepsilon+b\bar\varepsilon\mathbf1$, $a=\sqrt{1-\rho}$, $b=-a+\sqrt{a^2+N\rho}$, $\varepsilon$ i.i.d. standard normal. Tested $N=3,20,500$ at $q=0.05$.

(b) Random frame: $N=100$ i.i.d. uniform unit vectors $u_i\in\mathbb R^3$ (seed 1), $\Sigma_{ij}=u_i\cdot u_j$ (rank 3, mixed signs, many weakly correlated directions), $\Sigma\circ\Sigma=$ Gram of $u_i\otimes u_i$, $Z_t=\sqrt{1-t}\,U g+\sqrt t\,(U\otimes U)h$.

## Checks

### H1

The family is taken along $q\to0$ (tested at $q=0.05$; see NOT for why the scale is $q$).

### H2

$N$ is a positive integer.

### H3

Both are Gram matrices of unit vectors, hence in $\mathcal C_N$ (singular).

### NOT

NOT requires $\mathcal V_-(f_{q,\Sigma})>1/8$, since $\mathcal M(q)\ge0$.

(a) The path is monotone in $\rho$ over an interval of length $O(1/N)$ around $0$. Numerical (Monte Carlo, common random numbers, 26-point grid): $q=0.05$, $N=3$: $f\in[0.0491,0.0510]$, $\mathcal V_-=0.0020$; $N=20$: $f\in[0.0498,0.0506]$, $\mathcal V_-=0.0012$; $N=500$: $f\in[0.0494,0.0504]$, $\mathcal V_-=0.0008$ (noise level). Heuristically $\bar\varepsilon=O(N^{-1/2})$ shifts thresholds of size $\sqrt{2\log N}$ by a vanishing amount, so $f\to q$ uniformly in $t$ as $N\to\infty$.

(b) $f\in[0.0267,0.0289]$ at $q=0.05$, $\mathcal V_-\approx0.0026$ (noise level).

In both cases $\mathcal V_-\le0.05\,q\ll1/8$. NOT fails (numerically).

## Failure

NOT fails: the simplex path moves the equicorrelation only by $O(1/N)$ near $0$ and the profile stays within a few percent of $q$; random 3-frames likewise give $\mathcal V_-\approx0.05q$.
