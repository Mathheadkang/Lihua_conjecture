---
type: candidate
title: >-
  Arbitrarily weak negative residual equicorrelation fails infinite PSD
  extendibility
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: fail
  H5: unknown
  H6: unknown
  H7: unknown
  NOT: unknown
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:56:29.475Z'
extension_version: 0.0.4
---

## Object

Set $\sigma=1/2$, $q=1/10$, and $\eta=\delta=1$. Take the proposed deterministic parameter array
$$
\theta_i=0,\qquad \ell_i=1,\qquad C_{ii}=1,\qquad C_{ij}=-1/100\quad(i\ne j).
$$
The proposed parameter law is the point mass at this array. The intended test is whether arbitrarily weak negative residual equicorrelation, which is admissible in many finite dimensions, can enter the cross-dimension law space at its PSD boundary. This differs from the board's antipodal Gram family: here every off-diagonal entry has the same negative sign, with no sign-product Gram representation.

## Checks

### H1

Pass. The selected parameters satisfy $0<\sigma<1$, $0<q\le S(1)<1/2$, and $\eta,\delta>0$.

### H2

Pass. Every coordinate mark is $(0,1)$, so it belongs to $E_{\rm mark}$ and is canonical.

### H3

Pass. The proposed residual array is symmetric, its entries lie in $[-1,1]$, and its diagonal entries equal one.

### H4

Fail. Every finite principal residual matrix must be positive semidefinite. The $n$-coordinate principal matrix is
$$
C_n=\frac{101}{100}I_n-\frac1{100}\mathbf1\mathbf1^{\mathsf T}.
$$
Its eigenvalues are $101/100$ on $\mathbf1^\perp$ and $(101-n)/100$ on $\operatorname{span}\{\mathbf1\}$. Thus the matrices are positive semidefinite through $n=101$, including a singular boundary matrix at $n=101$, but fail positive semidefiniteness at $n=102$. Explicitly,
$$
\mathbf1^{\mathsf T}C_{102}\mathbf1=-102/100<0.
$$
Consequently the proposed point mass is not a law in $\mathfrak P$; the later checks are not performed. More generally, replacing $1/100$ by any $\varepsilon>0$ merely postpones the first negative eigenvalue until $n>1+1/\varepsilon$, so approaching zero negative residual correlation does not repair the infinite-array hypothesis.

### H5

Unknown. Joint exchangeability was not checked after the first failure.

### H6

Unknown. Independence from Gaussian innovations was not checked after the first failure.

### H7

Unknown. Finite second moment, required for the penalized optimizer conclusions, was not checked after the first failure.

### NOT

Unknown. No conclusion was tested after the failure of H4.

## Failure

H4 fails: constant strictly negative off-diagonal residual correlation cannot define a positive semidefinite array in all finite dimensions.
