---
type: candidate
title: >-
  Singular regular-simplex Gaussian family at the negative equicorrelation
  boundary
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:24:10.657Z'
extension_version: 0.0.4
---

## Object

For every integer $N\ge2$, take independent standard normal variables $Z_1,\ldots,Z_N$, put $\bar Z=N^{-1}\sum_iZ_i$, and set
$$
T_i=\sqrt{\frac{N}{N-1}}(Z_i-\bar Z).
$$
Use any $0<q\le1/(2e)$ and $p_i=\overline\Phi(T_i)$, with the ordinary Simes event $E_q=\{\exists k:p_{(k)}\le qk/N\}$. In particular, $N$ can tend to infinity as $q\downarrow0$ without any rate restriction.

This family lies exactly at the positive-semidefinite boundary of negative equicorrelation, has rank $N-1$, and has the deterministic constraint $\sum_i T_i=0$. For $N\ge3$ it is neither signed rank one nor a union of independent antipodal blocks: every pair of distinct coordinates has strictly negative covariance, whereas different independent blocks have covariance zero. Thus the board's earlier block calculation does not already dispose of this family.

## Checks

### H1

The dimension $N$ is a positive integer and is unbounded within this family.

### H2

The covariance is
$$
\Sigma=\frac{N}{N-1}\left(I_N-\frac{\mathbf1\mathbf1^{\mathsf T}}N\right).
$$
Its diagonal entries are one and its off-diagonal entries are $-1/(N-1)$. For every $x\in\mathbb R^N$,
$$
x^{\mathsf T}\Sigma x=\frac{N}{N-1}\sum_i(x_i-\bar x)^2\ge0.
$$
Hence $\Sigma\in\mathcal C_N$, including the permitted singular case. Its nonzero eigenvalues are $N/(N-1)$ with multiplicity $N-1$.

### H3

The displayed vector is a linear transformation of independent standard normals. It is exactly jointly Gaussian with mean zero and covariance $\Sigma$; all coordinates are true nulls.

### H4

Every displayed level satisfies $0<q<1/2$. To test any proposed sufficiently small range, take the intersection $0<q\le\min\{q_0,1/(2e)\}$; arbitrarily small levels remain available.

### H5

The p-values are exactly $\overline\Phi(T_i)$, with standard normal marginals. The event $E_q$ includes all ranks and uses non-strict comparisons and multiplicities as required. If
$$
K(t)=\#\{i:p_i\le t\},
$$
then $E_q=\bigcup_{k=1}^N\{K(qk/N)\ge k\}$ exactly.

### NOT

**Fail:** the entire family has $\mathbb P(E_q)\le2eq$ on the displayed level range, uniformly in $N$.

Here is a direct upper-orthant calculation. For a coordinate subset $A$ of size $k$ and $t\in(0,1)$, set $z=\overline\Phi^{-1}(t)$. Interpolate its correlation matrix by
$$
\Sigma_A(s)=(1-s)I_k+s\Sigma_A,\qquad 0\le s<1.
$$
This is positive definite, and its off-diagonal correlations decrease from zero. For a positive definite Gaussian vector, the derivative of $\mathbb P(X_i\ge z\text{ for all }i)$ with respect to an off-diagonal correlation $\rho_{ij}$, holding the other entries fixed, is
$$
\varphi_2(z,z;\rho_{ij})\,
\mathbb P(X_\ell\ge z\text{ for }\ell\ne i,j\mid X_i=X_j=z)\ge0.
$$
This identity follows by differentiating the Gaussian density with respect to $\rho_{ij}$, which equals its mixed derivative in coordinates $i,j$, and integrating both derivatives over $[z,\infty)$. Consequently the orthant probability is nonincreasing along $s$. At $s=0$ it equals $t^k$. Taking $s\uparrow1$ preserves the inequality, even for the singular endpoint: each coordinate has a continuous standard normal marginal, so the orthant boundary has probability zero. Therefore
$$
\mathbb P(p_i\le t\text{ for every }i\in A)\le t^k.
$$
If $K(t)\ge k$, some subset of size $k$ has all its p-values at most $t$. A union bound now gives
$$
\mathbb P(K(qk/N)\ge k)
\le {N\choose k}(qk/N)^k
\le(eq)^k,
$$
using ${N\choose k}\le(eN/k)^k$. Thus
$$
\mathbb P(E_q)\le\sum_{k=1}^N(eq)^k
\le\frac{eq}{1-eq}\le2eq,
\qquad 0<q\le1/(2e).
$$
The calculation actually covers any Gaussian correlation matrix whose off-diagonal entries are all nonpositive. It leaves matrices with mixed positive and negative correlations untreated. The family therefore supplies no divergent probability-to-level ratio and cannot refute the unspecified universal constant in the target.

## Failure

NOT fails: singular regular-simplex Gaussians obey $\mathbb P(E_q)\le2eq$ uniformly in dimension for $0<q\le1/(2e)$.
