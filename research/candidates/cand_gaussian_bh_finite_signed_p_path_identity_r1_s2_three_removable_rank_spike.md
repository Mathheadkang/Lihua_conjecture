---
type: candidate
title: Rank-one triple with an isolated non-strict rank spike
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:25:30.473Z'
extension_version: 0.0.4
---

## Object

Let $N=3$, $q=3/10$, $d=u(3/10)-u(1/10)$, $c=u(3/10)+u(1/10)$, $\theta=(0,d,c)$, and $\Sigma=vv^{\mathsf T}$ with $v=(1,1,-1)$. Realize $Z=(X,X,-X)$ using one standard normal $X$. At the first-coordinate path parameter $t=1/10$, all three p-values are $(1/10,3/10,3/10)$, giving an isolated largest BH rank three. The proposed failure mechanism is counting that isolated point as an actual jump.

## Checks

### H1

$N=3$ is finite and positive.

### H2

The means are finite and real. Since $d<0<c$, $I_0=\{1,2\}$ includes a strictly negative null.

### H3

$\Sigma=vv^{\mathsf T}$ is positive semidefinite, rank one, and unit diagonal. The displayed jointly Gaussian vector has that covariance. Residual vectors for both true-null indices are identically zero.

### H4

$q=3/10\in(0,1/2)$.

### NOT

Fail. Write
$$
a=S(u(1/5)-u(3/10)+u(1/10)),\qquad
b=S(u(3/10)+u(1/10)-u(1/5)).
$$
Numerically $a=0.05493560452018975$ and $b=0.16744004072060537$, with $a<1/10<b<1/5$. On the first-coordinate path the scores are $(u(t),u(t)+d,c-u(t))$. Away from endpoints of the following intervals, its actual BH ranks are
$$
R_1(t)=\begin{cases}
2,&0<t<a,\\
1,&a<t<1/10,\\
0,&1/10<t<b,\\
2,&b<t<1/5,\\
0,&1/5<t<3/10.
\end{cases}
$$
The rank at $t=1/10$ is three. Nevertheless $A_1((1/10)^-)=A_1((1/10)^+)=1$ while its point value is $1/3$. This is exactly a removable discrepancy, so $1/10\notin J_1$. The actual jumps are at $a$ and $b$, with signed sizes $-5a$ and $1-5b$. Endpoint limits, affine components, and the derivative formula follow directly from these intervals. With $g_1=1$, direct integration and the claimed identity both give
$$
F_1=\frac a2+(1/10-a)+\frac{1/5-b}{2}
=\frac15-\frac{a+b}{2}
=\frac1{10}\{1-5a+(1-5b)\}
\approx0.08881217737960245.
$$
For completeness, parameterize the second-null path by its p-value $s$. Then $t=S(u(s)-d)$ ranges over $(0,1/10)$ as $s$ ranges over $(0,3/10)$. Its rank is two for $s<1/5$ and one for $s>1/5$. Coordinate two is rejected only in the first interval. Thus $A_2(s)=\min\{5s,1\}$, with no jumps. Its negative-null density is $g_2(s)=\exp\{d u(s)-d^2/2\}$; integration by parts yields baseline $5\int_0^{1/5}g_2(s)\,ds=5a$, and the identity gives $F_2=a/2$, also the direct probability divided by two. This baseline lies in $[0,1]$ because $g_2\le1$ on this interval.

Every event is deterministic and finite, and every signed jump sum is bounded and integrable. The full FDR is $F_1+F_2=1/5-b/2$. The positive jump contributions are $B_1=1-5b$ and $B_2=0$, so the asserted upper bound holds as well. The isolated rank-three point changes no integral.

## Failure

NOT fails: merging actual net jumps and omitting the removable rank spike gives exactly the directly integrated FDR contributions for both true nulls.
