---
type: candidate
title: Harmonic disjoint clusters fail conditional sub-Poisson calibration
status: failed
target_asset: gaussian_bh_conditional_subpoisson_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: fail
  NOT: unknown
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:25:18.985Z'
extension_version: 0.0.4
---

## Object

Set $N=65536$, $q=1/25$, $I_0=\{1,\ldots,N\}$, $\mathcal H=\{\varnothing,\Omega\}$, and $K=1$. Draw $J\in\{0,\ldots,N\}$ with
$$
\mathbb P(J=j)=\frac{q}{j}\quad(1\le j\le N),\qquad
\mathbb P(J=0)=1-q\sum_{j=1}^N\frac1j.
$$
Given $J=j>0$, draw a uniformly random subset $S$ of size $j$ and set $P_i=qj/N$ for $i\in S$ and $P_i=1$ otherwise. Given $J=0$, set every p-value equal to $1$.

This is a disjoint-event harmonic cluster construction: a possible large BH rejection count has probability proportional to its reciprocal. It tests whether such a rank-selection pathology survives the additional conditional count hypothesis.

## Checks

### H1

Pass: $N$ is a positive integer, the original null set is deterministic, and $q\in(0,1)$. The sampling law is normalized with nonnegative probabilities, since
$$
\sum_{j=1}^N\frac1j\le1+\log N<17<25.
$$
Every p-value lies in $[0,1]$.

### H2

Pass: $\mathcal H$ is a conditioning sigma-field and there are no alternative coordinates, so it contains the complete, empty alternative vector.

### H3

Pass: use ordinary BH with the specified largest rank and non-strict comparisons. On $J=j>0$, the first $j$ order statistics equal $qj/N$; rank $j$ qualifies by equality. For every $k>j$ the order statistic is $1>qk/N$, so the actual rejection count is $R=j$, with all original labels retained. On $J=0$ there are no rejections.

### H4

Pass: $K=1$ is $\mathcal H$-measurable and belongs to $[1,\infty]$.

### H5

Fail: the required conditional count mgf inequality must hold at every deterministic threshold and every nonnegative exponent. At
$$
s=\frac{2q}{N}=\frac1{819200},\qquad \lambda=\log2,
$$
the null count equals $1$ on $J=1$, equals $2$ on $J=2$, and equals $0$ on every other event. Hence, because conditioning is trivial,
$$
\mathbb E[e^{\lambda C(s)}\mid\mathcal H]
=1+\frac1{25}(2-1)+\frac1{50}(4-1)
=\frac{11}{10}.
$$
The claimed upper bound at this threshold would be
$$
\exp\{NKs(e^\lambda-1)\}=\exp\{2/25\}
<\frac1{1-2/25}=\frac{25}{23}<\frac{11}{10}.
$$
Thus the first failing hypothesis is the sub-Poisson mgf inequality, even though the aggregate first moment at this grid point satisfies $\mathbb E[C(s)]=2q=Ns$ exactly.

### NOT

Unknown: checking stopped at H5; the conclusion-failure check was not performed.

## Failure

H5 fails: disjoint harmonic clusters have $\mathbb E[2^{C(2q/N)}]=11/10>\exp(2/25)$, violating the required count mgf bound.
