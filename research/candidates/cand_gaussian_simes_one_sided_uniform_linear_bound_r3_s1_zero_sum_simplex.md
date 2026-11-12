---
type: candidate
title: Singular zero-sum simplex Gaussian family
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
slot: 1
direction: boundary_degenerate
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:24:10.657Z'
extension_version: 0.0.4
---

## Object

For every integer $N\ge4$, take independent standard normals $Z_1,\ldots,Z_N$, put $\bar Z=N^{-1}\sum_i Z_i$, and define
$$
T_i=\sqrt{\frac{N}{N-1}}(Z_i-\bar Z).
$$
Thus $\sum_iT_i=0$ identically. Let $\Sigma_N$ have diagonal entries one and every off-diagonal entry $-1/(N-1)$. Allow $N$ to grow arbitrarily with $q$, and take $0<q\le1/(2e)$. Set $p_i=\overline\Phi(T_i)$ and let $E_q$ be the actual Simes event with multiplicities and non-strict comparisons.

This tests the singular, maximally negative equicorrelation boundary. It is not a signed rank-one family, independent antipodal-block family, or regular planar polygon: its rank is $N-1$ and every pair has strictly negative covariance.

## Checks

### H1

Pass: $N$ is a positive integer, with no upper bound.

### H2

Pass: writing $\mathbf1$ for the all-ones vector,
$$
\Sigma_N=\frac{N}{N-1}\left(I_N-\frac{\mathbf1\mathbf1^{\mathsf T}}N\right).
$$
The parenthesized matrix is an orthogonal projection. Hence $\Sigma_N$ is symmetric positive semidefinite with unit diagonal, zero eigenvalue on $\mathbf1$, and eigenvalue $N/(N-1)$ on its orthogonal complement. It belongs to $\mathcal C_N$ and is singular.

### H3

Pass: $T$ is a deterministic linear transformation of independent centered Gaussian variables and has covariance $\Sigma_N$. In particular its mean is exactly zero and every marginal is standard normal.

### H4

Pass: $0<q\le1/(2e)<1/2$. This covers an entire interval tending to zero, with $N$ allowed to vary freely.

### H5

Pass: use exactly $p_i=\overline\Phi(T_i)$ and
$$
E_q=\bigcup_{k=1}^N\left\{\#\{i:p_i\le qk/N\}\ge k\right\}.
$$
This identity includes multiplicities and uses the specified non-strict comparisons; it is equivalent to the existence of any qualifying BH rank, without replacing the actual event by a different rejection rule.

### NOT

Fail: the family has a dimension-uniform linear bound. First, for any subset $A$ of $k$ coordinates and $u\in(0,1)$,
$$
\mathbb P(p_i\le u\text{ for every }i\in A)\le u^k.
$$
Here is an interpolation proof of this inequality. Put $c=\overline\Phi^{-1}(u)$ and $f_\varepsilon(x)=\Phi((x-c)/\varepsilon)$, so $0\le f_\varepsilon\le1$ and $f'_\varepsilon\ge0$. Interpolate the covariance of the selected coordinates from $I_k$ to their actual covariance by $Q(s)=I_k+s(\Sigma_{N,A}-I_k)$. For $0\le s<1$ this is positive definite. Gaussian integration by parts gives
$$
\frac{d}{ds}\mathbb E_{Q(s)}\prod_{i\in A}f_\varepsilon(X_i)
=\sum_{i<j,\ i,j\in A}(\Sigma_N)_{ij}\,
\mathbb E_{Q(s)}\left[f'_\varepsilon(X_i)f'_\varepsilon(X_j)
\prod_{\ell\in A\setminus\{i,j\}}f_\varepsilon(X_\ell)\right]\le0.
$$
All factors inside the expectation are nonnegative and all displayed covariances are negative. Integrate in $s$, take the covariance limit $s\uparrow1$, then $\varepsilon\downarrow0$. Marginals have no atom at $c$, so the result holds for the non-strict event. At $s=0$ the probability factors and equals $u^k$.

A union bound over subsets and then over qualifying ranks consequently gives
$$
\begin{aligned}
\mathbb P(E_q)
&\le\sum_{k=1}^N\binom Nk(qk/N)^k\\
&\le\sum_{k=1}^N(eq)^k
\le\frac{eq}{1-eq}\le2eq.
\end{aligned}
$$
Thus $\mathbb P(E_q)/q\le2e$ simultaneously for all dimensions in this family and all $0<q\le1/(2e)$. Even arbitrary growth of $N$ and exact singularity cannot produce the unbounded small-level ratio required to refute the conjecture. This establishes only a bound for this family, not the optimal constant or the conjecture for mixed-sign covariances.

## Failure

NOT fails: the singular zero-sum simplex family has $\mathbb P(E_q)\le2eq$ uniformly in dimension for $0<q\le1/(2e)$.
