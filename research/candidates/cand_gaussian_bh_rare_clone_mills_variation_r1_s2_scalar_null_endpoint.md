---
type: candidate
title: Scalar zero-null endpoint and fractional-rank test
status: failed
target_asset: gaussian_bh_rare_clone_mills_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-08T23:56:28.396Z'
extension_version: 0.0.4
---

## Object

Take the smallest model: $N=d=1$, $q=S(1)$, $\theta_1=0$, $\Sigma=(1)$, $v_1=1$, and $i=1$. Thus $U=u_1=1$, $m=m(1)=S(1)/\phi(1)$, $L=1/m-1$, and the sole original and cloned coordinates are true nulls. Use exactly the specified offset distribution and midpoint quantiles, with $0<\varepsilon<\min\{1/4,1/(2L)\}$. The proposed failure was that a positive fractional crossing, or the endpoint rank one, could change the first variation even in this scalar model.

## Checks

### H1

Pass. The original size is the fixed positive integer $N=1$.

### H2

Pass. $q=S(1)=0.15865525393145705$ lies strictly between zero and one half.

### H3

Pass. The fixed mean $\theta=(0)$ is permitted, including the chosen zero-mean true null.

### H4

Pass. The covariance $(1)$ is positive definite with unit diagonal.

### H5

Pass. $G\sim N(0,1)$ and $T_1=G$ give the required finite-dimensional unit-direction representation.

### H6

Pass. The chosen index is $i=1\in[1]$, and its original one-sided label is $\ell_1=1$.

### H7

Pass. All offsets and parameter measures are exactly those in the defining model. The displayed range of $\varepsilon$ guarantees $\varepsilon L<1$; there is no positive-mean restriction to check.

### NOT

Fail. The scalar model has the stated limit and coefficient, including positive ranks below one. Here is an explicit check that keeps the global crossing.

Integration by parts gives
$$
\int_1^\infty\phi(v)v^{-2}\,dv=\phi(1)-S(1),
$$
so the nonzero mass is exactly $\varepsilon L$ and the zero atom is $a=1-\varepsilon L$. The continuous transformation $d=\varepsilon(1-1/v)$ has no endpoint atom and has values in $(0,\varepsilon)$. All clone means are nonpositive, all marginal variances are one, and exact copies have the original FDR $F=q$.

Let $u(x)=S^{-1}(qx)$ and
$$
z(v)=q^{-1}\{\phi(v)/v-S(v)\},\qquad v\ge1.
$$
Above the zero atom the distribution is parameterized by
$$
x(v)=1-\varepsilon z(v),\qquad
Q_\varepsilon(x(v))=\varepsilon(1-1/v).
$$
The scalar population has a positive crossing exactly when $T_1$ exceeds the global threshold
$$
M_\varepsilon=\inf_{0<x<1}\{u(x)+Q_\varepsilon(x)\}.
$$
The zero-atom part of the objective decreases to $u(a)$. On the continuous part its derivative with respect to $v$ is
$$
\frac{\varepsilon}{v^2}\left\{1-\frac{\phi(v)}{\phi(u(x(v)))}\right\}.
$$
Since $v$ increases and $u(x(v))$ decreases, this has exactly one sign change, from negative to positive, at $v=v_\varepsilon$ characterized by
$$
(1-\varepsilon)S(v_\varepsilon)+\varepsilon\phi(v_\varepsilon)/v_\varepsilon=q.
$$
The left side is strictly decreasing, with derivative $-\phi(v)(1+\varepsilon/v^2)$; hence this is the global minimizer and $v_\varepsilon>1$. Thus
$$
M_\varepsilon=v_\varepsilon+\varepsilon(1-1/v_\varepsilon),\qquad
M_\varepsilon=1+\varepsilon(1-m)+O(\varepsilon^2).
$$
For fixed $\varepsilon$, a finite-copy crossing exists exactly when
$$
T_1\ge M_{K,\varepsilon}:=\min_{1\le k\le K}\{S^{-1}(qk/K)+Q_\varepsilon((k-1/2)/K)\}.
$$
These minima converge to $M_\varepsilon$: the offset quantile is continuous across its zero-atom boundary and on $(0,1)$, tends to $\varepsilon$ at one, and $u(x)$ diverges at zero. All rejected coordinates are null, so the finite FDP is the indicator of this event and its FDR tends to $S(M_\varepsilon)$. At a positive largest population crossing, $H=x$ by right continuity and the supremum property; the resulting FDP is one even when the rank is below one. If $H(1)=1$, the largest crossing is the permitted endpoint one.

The sole signed face jump is $\Delta_{1,1}=1$ and $\mu_{1,1}(E_1)=\phi(1)$. Consequently
$$
\lim_{\varepsilon\downarrow0}\frac{S(M_\varepsilon)-q}{\varepsilon}
=-(1-m)\phi(1),
$$
exactly the asserted signed inverse-Mills expression. A short standard-library bisection diagnostic gives difference quotients $-0.0833140487784$, $-0.0833154562568$, and $-0.0833154704447$ for $\varepsilon=10^{-2},10^{-3},10^{-4}$, respectively, versus the predicted $-0.0833154705877$.

Finally, the continuous parameter-measure TV distance is precisely $\varepsilon L$ and its first transport moment is at most $\varepsilon^2 L$. Midpoint rounding changes the nonzero count by at most one, so the finite-copy TV and transport bounds hold with $\varepsilon L+1/K$ and $\varepsilon(\varepsilon L+1/K)$, respectively. Thus none of the four conclusions fails in this test.

## Failure

NOT fails: the scalar zero-null model retains the actual common crossing and gives exactly the proposed derivative; fractional ranks and the endpoint create no counterexample.
