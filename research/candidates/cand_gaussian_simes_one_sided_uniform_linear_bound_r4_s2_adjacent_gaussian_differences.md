---
type: candidate
title: Adjacent Gaussian differences with growing dimension
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
round: 4
slot: 2
direction: small_cases
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:29:07.926Z'
extension_version: 0.0.4
---

# Adjacent Gaussian differences with growing dimension

## Object

For every positive integer $m$, put $N=2m$. Let $Z_0,\ldots,Z_N$ be independent standard normal variables and set
$$
T_i=\frac{Z_i-Z_{i-1}}{\sqrt 2},\qquad 1\le i\le N.
$$
The covariance matrix has diagonal entries one, entries $-1/2$ immediately above and below the diagonal, and all other entries zero. Use $p_i=\overline\Phi(T_i)$ and ordinary BH at any $0<q<1/2$, allowing $m$ to grow arbitrarily as $q$ tends to zero.

This family has an unbounded number of distinct Gaussian coordinates and overlapping latent variables. Its adjacent coordinates are dependent, so it is not a family of independent antipodal blocks. The covariance is not the regular-simplex covariance. The new feature tested here is a chain of the smallest nontrivial local overlaps; the argument below uses an independent partition into two classes.

## Checks

### H1

The dimension $N=2m$ is a positive integer and is unbounded over this family.

### H2

The displayed covariance is symmetric, has diagonal entries one, and is positive semidefinite because, for every $a\in\mathbb R^N$,
$$
a^{\mathsf T}\Sigma a
=\frac12\left(a_1^2+\sum_{j=1}^{N-1}(a_j-a_{j+1})^2+a_N^2\right)\ge0.
$$
In fact it is positive definite: equality forces every $a_j=0$.

### H3

The vector $T$ is a linear transformation of independent centered Gaussian variables, and hence is exactly jointly centered Gaussian with the stated covariance. Every coordinate has variance one.

### H4

Every $q\in(0,1/2)$ is permitted in this family, including arbitrarily small levels. In particular the estimates below hold throughout $0<q\le q_0$ for $q_0=1/4$.

### H5

The p-values are precisely the target's one-sided p-values. Each is standard uniform. Let
$$
E_q=\{\exists k\in\{1,\ldots,2m\}:p_{(k)}\le qk/(2m)\},
$$
where multiplicities are retained and comparisons are non-strict, exactly as in the target.

### NOT

This check fails: the ratio $\mathbb P(E_q)/q$ is at most two uniformly in $m$ and $q$.

Let $O=\{1,3,\ldots,2m-1\}$ and $D=\{2,4,\ldots,2m\}$. Within either class the underlying pairs $(Z_{i-1},Z_i)$ are disjoint. Thus each class contains $m$ mutually independent standard-uniform p-values, although the two classes need not be independent of one another.

If $E_q$ occurs at rank $k$, at least $k$ p-values are at most $qk/(2m)$. One class has $\ell\ge k/2$ such p-values. Its $\ell$-th order statistic therefore obeys
$$
p^{\mathrm{class}}_{(\ell)}\le\frac{qk}{2m}\le\frac{q\ell}{m}.
$$
Consequently $E_q$ is contained in the union of the two classwise Simes events at level $q$.

For completeness, each independent class has Simes probability exactly $q$. Here is an elementary derivation that does not assume independence between the classes. For $m$ independent uniform p-values let $R$ be the ordinary BH rejection count at level $q$. For coordinate $i$, let $R_i^0$ be the rejection count after replacing only its p-value by zero. This count is at least one and depends only on the other p-values. Deterministically,
$$
\{i\text{ is rejected}\}=\{p_i\le qR_i^0/m\},
\qquad R=R_i^0\text{ on this event}.
$$
Indeed, setting an already rejected coordinate to zero leaves all order statistics beyond the last crossing unchanged. Conversely, restoring a p-value at most $qR_i^0/m$ preserves a crossing at $R_i^0$, and monotonicity prevents a larger rejection count. Also ordinary BH has exactly $R$ rejected coordinates: more than $R$ p-values at most $qR/m$ would yield a larger crossing. Conditioning on the other p-values now gives
$$
\mathbb E\left[\frac{\mathbf1\{i\text{ is rejected}\}}{R\vee1}\right]
=\mathbb E\left[\frac{qR_i^0/m}{R_i^0}\right]
=\frac qm.
$$
Summing over $i$ proves $\mathbb P(R\ge1)=q$. The classwise union bound consequently yields
$$
\mathbb P(E_q)\le q+q=2q.
$$
This holds with no restriction on the growth of $m$. Thus the family cannot produce the unbounded rejection-probability-to-level ratio needed to refute an unspecified finite universal linear constant. The argument only establishes a bound for this family.

## Failure

NOT fails: odd and even coordinates separately have independent uniform p-values, so every full BH crossing forces a classwise crossing and $\mathbb P(E_q)\le2q$ uniformly in dimension.
