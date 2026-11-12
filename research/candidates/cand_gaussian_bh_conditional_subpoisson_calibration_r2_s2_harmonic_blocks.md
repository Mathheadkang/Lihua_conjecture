---
type: candidate
title: Harmonic rare-rank blocks fail sub-Poisson calibration
status: failed
target_asset: gaussian_bh_conditional_subpoisson_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: fail
  NOT: unknown
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:25:18.985Z'
extension_version: 0.0.4
---

## Object

Set $N=2^{16}$, $I_0=\{1,\ldots,N\}$, and $q=1/100$. Let $J$ take values $0,1,\ldots,N$, with $\mathbb P(J=r)=q/r$ for $1\le r\le N$ and $\mathbb P(J=0)=1-qH_N$, where $H_N=\sum_{r=1}^N1/r$. On $J=r>0$, put $P_i=qr/N$ for $i\le r$ and $P_i=1$ for $i>r$. On $J=0$, put every $P_i=1$. Take the trivial conditioning sigma-field and $K=1$.

This large-rank mixture is motivated by its threshold first moments: at $s=qk/N$, $\mathbb E C(s)=\sum_{r=1}^k(q/r)r=qk=Ns$. The exponential count requirement must still be checked.

## Checks

### H1

Pass. The specified $N$ is a positive integer, $I_0$ is deterministic, $q\in(0,1)$, and every p-value belongs to $[0,1]$. The probabilities are valid because $H_N\le1+\log N<13$, hence $qH_N<13/100<1$.

### H2

Pass. There are no alternative coordinates, so the trivial sigma-field contains the complete alternative vector.

### H3

Pass. The constant $K=1$ is measurable and belongs to $[1,\infty]$.

### H4

Fail. At the deterministic threshold $s=2q/N$, the count equals $1$ on $J=1$, $2$ on $J=2$, and $0$ on all other outcomes. For $\lambda=\log 2$,

$$
\mathbb E e^{\lambda C(s)}
=1+q(2-1)+\frac q2(4-1)
=1+\frac{5q}{2}=\frac{41}{40}.
$$

The proposed sub-Poisson upper bound is

$$
\exp\{NKs(e^\lambda-1)\}=e^{2q}=e^{1/50}
<\frac{1}{1-1/50}=\frac{50}{49}<\frac{41}{40}.
$$

Thus this law violates the count hypothesis despite satisfying its first-moment consequence exactly at every BH threshold.

### NOT

Unknown. Checking stops at H4.

## Failure

H4 fails: the harmonic rare-rank mixture has an excessive exponential count moment already at the second BH threshold.
