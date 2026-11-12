---
type: candidate
title: Harmonic extremizer with Gaussian marginals
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: fail
  H6: unknown
  H7: unknown
  H8: unknown
  NOT: unknown
mode: refute
round: 2
slot: 2
direction: known_counterexamples
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:13:28.581Z'
extension_version: 0.0.4
---

## Object

This candidate tests Gaussian quantile transformation of a harmonic arbitrary-dependence construction. The motivating related pathology is the logarithmic inflation obtainable with non-Gaussian adversarial p-values, discussed in the introduction of [Lei (2026), arXiv:2607.14812v4](https://arxiv.org/html/2607.14812v4#S1) and Theorem 19 of [Chi, Ramdas and Wang, arXiv:2212.09706v4](https://arxiv.org/html/2212.09706v4#S5). The explicit all-null construction below is specified independently; it is not asserted to be the exact construction in either source.

For each $q\in(0,1/4)$ put $N=\lfloor q^{-1}\rfloor$ and $H_N=\sum_{k=1}^{N}k^{-1}$. Choose a categorical variable $K\in\{0,1,\ldots,N\}$ with
$$
\mathbb P(K=k)=q/k\quad(1\le k\le N),\qquad \mathbb P(K=0)=1-qH_N.
$$
Independently choose $W$ uniform on $(0,1)$. Conditional on $K=k\ge1$, choose $S$ uniformly among the $k$-element subsets of $[N]$, independently of $W$. For $K=0$ put $S=\varnothing$. Define
$$
U_i=
\begin{cases}
q(K-1+W)/N,&i\in S,\\
q+(1-q)W,&i\notin S,
\end{cases}
\qquad
T_i=\overline\Phi^{-1}(U_i).
$$
The proposed model has $\theta=0$ and $\Sigma_{ij}=\mathbb E[T_iT_j]$. It proposes ordinary one-sided BH on these $T_i$ at level $q$.

## Checks

### H1

All levels are in $(0,1)$ and can tend to zero; the parameters may vary with $q$. The categorical law is legitimate, since
$$
qH_N\le q(1+\log N)\le q\{1+\log(1/q)\}<1.
$$
The final strict inequality follows from $\log x<x-1$ for $x=1/q>1$. All $U_i$ lie strictly between zero and one almost surely, so all $T_i$ are finite almost surely.

### H2

$N=\lfloor q^{-1}\rfloor\ge4$ is a finite positive integer at every level, and $N\to\infty$ as $q\downarrow0$.

### H3

Every $U_i$ is exactly uniform on $(0,1)$. Indeed, for $1\le k\le N$,
$$
\mathbb P(K=k,\ i\in S)=(q/k)(k/N)=q/N.
$$
On this event $U_i$ is uniform on $\bigl(q(k-1)/N,qk/N\bigr)$. The resulting density is one on each of these intervals, which partition $(0,q)$. The total probability of $i\notin S$ is $1-q$, and its value $q+(1-q)W$ is uniform on $(q,1)$, again giving density one. Thus $T_i$ has the standard normal marginal distribution, its mean is zero and its variance is one. In particular $\theta=0\in\mathbb R^N$.

### H4

The matrix $\Sigma$ exists because the coordinates have finite second moments. It is symmetric with unit diagonal, and
$$
x^{\mathsf T}\Sigma x=\mathbb E\left[\left(\sum_{i=1}^{N}x_iT_i\right)^2\right]\ge0.
$$
Hence $\Sigma\in\mathcal C_N$.

### H5

**Fail: the observation vector is not jointly Gaussian.** On $\{K=0\}$ all $U_i$ and hence all $T_i$ coincide. Therefore
$$
\mathbb P(T_1-T_2=0)\ge1-qH_N>0.
$$
But $\mathbb P(K=1,S=\{1\})=q/N>0$. On that event $U_1<q/N<q<U_2$, so $T_1>T_2$. The symmetric event with $S=\{2\}$ has the same positive probability and gives $T_1<T_2$. Thus $T_1-T_2$ is nonconstant, yet has an atom at zero.

If $T$ were jointly Gaussian, $T_1-T_2$ would be a centered normal random variable. A positive-variance normal law has no atoms, while a zero-variance normal law is constant. Both possibilities contradict the two facts just proved. Gaussian marginals and a valid covariance matrix therefore do not establish the exact joint-Gaussian hypothesis.

### H6

Unknown: the prescribed one-sided p-value and true-null check is not reached after H5 fails.

### H7

Unknown: the ordinary BH check is not reached after H5 fails.

### H8

Unknown: the FDR check is not reached after H5 fails.

### NOT

Unknown: no conclusion-violation check is made for this inadmissible observation law.

## Failure

H5 fails: the difference of two coordinates has an atom at zero and is nonconstant, which is impossible for a jointly Gaussian observation vector.
