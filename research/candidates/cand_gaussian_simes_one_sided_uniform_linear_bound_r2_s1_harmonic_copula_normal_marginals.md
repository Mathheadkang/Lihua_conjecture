---
type: candidate
title: Harmonic interval-subset copula transformed to normal marginals
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  NOT: unknown
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:20:28.439Z'
extension_version: 0.0.4
---

## Object

For every integer $N\ge2$, put $H_N=\sum_{k=1}^N1/k$ and $q_N=(4H_N)^{-1}$. Define a random integer $K$ by
$$
\mathbb P(K=0)=\frac34,\qquad \mathbb P(K=k)=\frac{q_N}{k},\quad 1\le k\le N.
$$
Conditional on $K=k\ge1$, choose $A$ uniformly among the $k$-element subsets of $[N]$ and draw independent variables
$$
U_k\sim\operatorname{Unif}(((k-1)q_N/N,kq_N/N)),\qquad V\sim\operatorname{Unif}((q_N,1)).
$$
Set $P_i=U_k$ for $i\in A$, and $P_i=V$ otherwise. When $K=0$, draw $V$ with the same law and set every $P_i=V$. Finally define
$$
T_i=\overline\Phi^{-1}(P_i),\qquad \Sigma_{ij}=\mathbb E[T_iT_j].
$$
This concrete multiscale copula tests whether making all marginal statistics exactly standard normal suffices to transport an arbitrary-dependence pathological family into the Gaussian model.

## Checks

### H1

Pass: $N$ is a positive integer, and the sequence permits unbounded dimension.

### H2

Pass: $\Sigma\in\mathcal C_N$. To establish the moments defining $\Sigma$, fix a coordinate $i$. For each $1\le k\le N$,
$$
\mathbb P(K=k,\ i\in A)=\frac{q_N}{k}\frac{k}{N}=\frac{q_N}{N}.
$$
The corresponding conditional value is uniform on an interval of length $q_N/N$. These disjoint intervals partition $(0,q_N)$, so the marginal density of $P_i$ is one there. Coordinate $i$ is inactive with total probability $1-q_N$ and then has the independent uniform law on $(q_N,1)$, also giving marginal density one. Thus $P_i\sim\operatorname{Unif}(0,1)$, and $T_i\sim\mathcal N(0,1)$ marginally. Consequently $\Sigma$ is symmetric with diagonal one and finite entries. For every $x\in\mathbb R^N$,
$$
x^{\mathsf T}\Sigma x=\mathbb E\left[\left(\sum_{i=1}^N x_iT_i\right)^2\right]\ge0.
$$

### H3

Fail: the vector $T$ is not jointly Gaussian, even though all its marginals are exactly standard normal. Let $D=T_1-T_2$. On $K=0$, both coordinates equal $\overline\Phi^{-1}(V)$, so
$$
\mathbb P(D=0)\ge\frac34>0.
$$
On the event $K=1$ and $A\in\{\{1\},\{2\}\}$, exactly one of $P_1,P_2$ belongs to $(0,q_N/N)$ while the other belongs to $(q_N,1)$. They are unequal. This event has probability $2q_N/N>0$, hence
$$
\mathbb P(D\ne0)\ge\frac{2q_N}{N}>0.
$$
If $T$ were centered jointly Gaussian, $D$ would be a centered univariate normal variable. Such a variable is either identically zero or has no atoms, contradicting the two displayed inequalities. Singularity of the allowed Gaussian covariance does not remove this contradiction.

### H4

Unknown: the testing-level hypothesis is not checked after H3 fails.

### H5

Unknown: the required one-sided p-value and ordinary non-strict Simes-event hypothesis is not checked after H3 fails.

### NOT

Unknown: the target conclusion is not tested after H3 fails.

## Failure

H3 fails because the difference of two coordinates has both an atom at zero and positive probability of being nonzero, excluding every jointly Gaussian law.
