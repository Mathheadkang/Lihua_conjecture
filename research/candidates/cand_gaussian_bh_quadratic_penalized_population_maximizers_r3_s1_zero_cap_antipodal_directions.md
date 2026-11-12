---
type: candidate
title: >-
  Zero moment cap with antipodal directions cannot escape Wasserstein
  compactness
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:52:05.960Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/\sqrt2$, $d=1$, and the boundary moment cap $C=0$. Write
$$
x_{v,\ell}=(0,v,\ell),\qquad v\in\{-1,1\},\quad\ell\in\{0,1\}.
$$
Consider the entire four-atom probability simplex
$$
\pi_a=\sum_{v\in\{-1,1\}}\sum_{\ell\in\{0,1\}}a_{v,\ell}\delta_{x_{v,\ell}},
\qquad a_{v,\ell}\ge0,\qquad\sum_{v,\ell}a_{v,\ell}=1.
$$
The attempted failure is noncompactness at the boundary $C=0$ caused by changing antipodal directions or labels. This tests compactness, rather than the previously tested canonical approximation of a fixed zero-mean mixed-tag law.

## Checks

### H1

Pass. The fixed parameters satisfy $q\in(0,1/2)$, $\sigma\in(0,1)$, and the positive finite dimension condition $d=1$.

### H2

Pass. Each of the four parameters belongs to the closed tagged domain: both tags permit mean zero, and $|v|=1$. Every $\pi_a$ is a deterministic Borel probability measure independent of the Gaussian variables. Its first and second mean moments are zero, so it belongs to $\mathcal P_2(\mathcal E)$.

### H3

Pass. The cap $C=0$ is finite and allowed. Every displayed law has $M_2(\pi_a)=0\le C$. Conversely, a law with $M_2=0$ has $\theta=0$ almost surely, since $\theta^2$ is nonnegative. In dimension one the only unit directions are $-1$ and $1$, so the displayed simplex is exactly $\mathcal K_0$.

### NOT

Fail. At these four points the metric is
$$
c(x_{v,\ell},x_{w,k})=|v-w|+\mathbf1_{\{\ell\ne k\}}\le3.
$$
For two simplex weights $a,b$, couple their common mass at each atom identically, and couple the remaining equal masses arbitrarily. The mass left to couple is $\frac12\sum_{v,\ell}|a_{v,\ell}-b_{v,\ell}|$. Therefore
$$
W_1(\pi_a,\pi_b)\le\frac32\sum_{v,\ell}|a_{v,\ell}-b_{v,\ell}|.
$$
Every sequence of simplex weights has a Euclidean convergent subsequence whose limit remains in the closed simplex. The displayed bound makes the associated measures converge in $W_1$ to a law in $\mathcal K_0$. Thus $\mathcal K_0$ is sequentially compact, hence compact in the metric $W_1$. It is also supported on a fixed finite set and is tight; $M_2$ is identically zero on this set. Varying the directions and tags at the zero cap does not violate the tested compactness or moment assertion. No claim about penalized maximizers is needed for this failed test.

## Failure

NOT fails: in dimension one the entire zero-cap set is a compact four-atom simplex, and its weight convergence explicitly controls Wasserstein distance.
