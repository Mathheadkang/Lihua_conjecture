---
type: candidate
title: Harmonic-event dependence with exact normal marginals fails joint Gaussianity
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: fail
  H3: unknown
  H4: unknown
  NOT: unknown
mode: refute
round: 3
slot: 4
direction: known_counterexamples
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:19:50.244Z'
extension_version: 0.0.4
---

## Object

This tests the classical harmonic-event dependence mechanism through a coordinatewise normal transformation. It is an inadmissible attempted object, not a Gaussian counterexample.

For $0<q<e^{-16}$ put $L=\log(1/q)$,
$$
N=\left\lceil e^{\sqrt L}\right\rceil,\qquad H_N=\sum_{k=1}^N\frac1k.
$$
Draw a categorical variable $K\in\{0,1,\ldots,N\}$ with
$$
\Pr(K=k)=\frac qk\quad(1\le k\le N),\qquad
\Pr(K=0)=1-qH_N.
$$
These probabilities are nonnegative in the specified range. If $K=k>0$, choose a subset $A\subseteq[N]$ of size $k$ uniformly. Conditional on $(K,A)$, draw the coordinates independently with
$$
P_i\sim\begin{cases}
\operatorname{Unif}(((k-1)q/N,kq/N)),&i\in A,\\
\operatorname{Unif}((q,1)),&i\notin A.
\end{cases}
$$
If $K=0$, all coordinates are independently uniform on $(q,1)$. Open interval endpoints have no effect on these continuous laws. Independently of everything, draw independent signs $S_i$ with probabilities $1/2$ at $-1$ and $1$. Define
$$
T_i=S_i\Phi^{-1}(1-P_i/2),\qquad \theta=0.
$$
There is no unspecified probability integral transform, rank replacement, or smoothing here: the conditional uniform intervals are part of the original exact object.

## Checks

### H1

For each $q$, $N=\lceil e^{\sqrt L}\rceil$ is finite, and $\theta=0$ is a deterministic vector in $\mathbb R^N$. Also
$$
H_N\le1+\log N\le\sqrt L+2,
$$
so $qH_N<1$ for $L\ge16$; hence the categorical probabilities defining the object are valid.

### H2

Fail: the coordinates have exact standard-normal marginals and covariance $I_N$, but are not jointly Gaussian.

First verify exact marginals, rather than assuming marginal validity from a discrete harmonic construction. For each fixed $i$ and each $k\in[N]$,
$$
\Pr(K=k,\ i\in A)=\frac qk\frac kN=\frac qN.
$$
This is exactly the length of $((k-1)q/N,kq/N)$. On that event the conditional density of $P_i$ on the interval is $N/q$. Thus its unconditional density is one on each of the $N$ intervals partitioning $(0,q)$. The total selected probability is $q$; on the complementary event of probability $1-q$, its conditional law is always uniform on $(q,1)$, so the density there is also one. Therefore each $P_i$ is exactly uniform on $(0,1)$, with no atoms.

It follows that $\Phi^{-1}(1-P_i/2)$ is exactly half-normal. Multiplication by the independent symmetric sign gives $T_i\sim\mathcal N(0,1)$. The independent centered signs also give, for $i\ne j$,
$$
\mathbb E[T_iT_j]=0,
$$
while $\mathbb E[T_i^2]=1$. Thus the covariance matrix is $I_N$, which is positive definite with unit diagonal.

Nevertheless, by the event construction,
$$
\Pr\!\left(\min_i P_i\le q\right)=\Pr(K>0)=qH_N.
$$
If the $T_i$ were jointly Gaussian with mean zero and covariance $I_N$, they would be independent, and their exact two-sided transforms $P_i=2\overline\Phi(|T_i|)$ would be independent uniforms. The same event would then have probability $1-(1-q)^N$. These probabilities differ strictly throughout the stated range. Indeed, writing $x=\sqrt L\ge4$ gives
$$
N\ge e^x>2(x+2)\ge2H_N,\qquad
Nq\le(e^x+1)e^{-x^2}<1.
$$
The elementary two-term inclusion-exclusion bound therefore gives
$$
1-(1-q)^N\ge Nq-\binom N2q^2
=Nq\{1-(N-1)q/2\}>Nq/2>qH_N.
$$
Hence this object violates the required joint Gaussianity. A valid covariance and exact Gaussian marginals do not repair that failure.

### H3

Unknown: not checked after the joint Gaussian hypothesis H2 failed.

### H4

Unknown: not checked after H2 failed.

### NOT

Unknown: not checked after H2 failed. No asymptotic violation within the admissible Gaussian class is claimed.

## Failure

H2 fails: the harmonic-event construction has exact standard-normal marginals and covariance $I_N$, but its dependent absolute-value events exclude joint Gaussianity.
