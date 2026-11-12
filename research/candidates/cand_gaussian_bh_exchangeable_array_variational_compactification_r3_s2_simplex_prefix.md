---
type: candidate
title: Three-coordinate simplex prefix with a nonextendible residual covariance
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  H6: unknown
  NOT: unknown
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:56:29.475Z'
extension_version: 0.0.4
---

## Object

Set $q=1/10$ and $\sigma=1/\sqrt3$. Attempt to use the deterministic infinite parameter array

$$
\theta_i=0,\qquad \ell_i=1,\qquad C_{ii}=1,\qquad C_{ij}=-1/2\quad(i\ne j).
$$

The first three residual coordinates are the Gram matrix of an equilateral simplex. This tests a finite-prefix extension obstruction, rather than the lawful iid two-atom antipodal population on the board: all distinct indices here are prescribed to have the same negative inner product. The attempted extension keeps this deterministic prescription at every size. It would make the observation covariance the identity, because $(1-\sigma^2)(-1/2)+\sigma^2=0$. Thus observation covariance positivity alone would fail to detect the residual-parameter obstruction.

## Checks

### H1

Pass: $0<\sigma=1/\sqrt3<1$ and $0<q=1/10<1/2$. In fact $q<S(1)$, so this level also lies in the normalized objective's level interval.

### H2

Pass: every mark is $(0,1)$ and belongs to the closed marked mean domain. These are canonical true-null labels.

### H3

Fail: lawfulness requires every finite residual principal matrix to be positive semidefinite, in addition to symmetry, entries in $[-1,1]$, and unit diagonal. For a prefix of size $n$,

$$
C_n=\frac32 I_n-\frac12\mathbf1_n\mathbf1_n^{\mathsf T}.
$$

Its eigenvalues are $3/2$ on the $(n-1)$-dimensional orthogonal complement of $\mathbf1_n$, and $(3-n)/2$ along $\mathbf1_n$. Prefix sizes one and two are positive definite, and size three is positive semidefinite with one zero eigenvalue. At size four,

$$
\mathbf1_4^{\mathsf T}C_4\mathbf1_4=-2<0.
$$

Consequently there is no lawful infinite parameter array with this prescription, even though the proposed observation covariance equals $I_n$ for every $n$. A Dirac law on this formal product array is not a member of $\mathfrak P$.

### H4

Unknown: joint exchangeability is not checked after H3 fails.

### H5

Unknown: parameter independence from Gaussian innovations and the required conditional observation construction are not checked after H3 fails.

### H6

Unknown: the finite-second-moment condition for penalized conclusions is not checked after H3 fails.

### NOT

Unknown: no conclusion is checked after H3 fails.

## Failure

H3 fails: the equilateral three-coordinate residual prescription has a negative eigenvalue at size four, so it cannot define a lawful exchangeable-array competitor.
