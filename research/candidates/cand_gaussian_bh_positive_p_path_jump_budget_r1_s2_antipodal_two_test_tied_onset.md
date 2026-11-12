---
type: candidate
title: Antipodal two-test family with a maximal tied rank-two onset
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:26:24.010Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$ and every $b\geq0$, let $N=2$, $Z=(X,-X)$ for $X\sim N(0,1)$, and
$$
\theta_1=-b,\qquad \theta_2=b+u(q)+u(q/2),\qquad
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$
Thus $I_0=\{1\}$. Both $q$ and $b$ may vary in this family. Its proposed source of large charge is a simultaneous disappearance of the rank-one qualification and appearance of the largest rank two at $t=q/2$.

## Checks

### H1

Pass: $N=2$ is a finite positive integer.

### H2

Pass: both means are finite real numbers for every admitted $q,b$. Because $u(q)\geq1$ and $u(q/2)>u(q)$, the second mean is strictly positive; the first mean is a true null, including strictly negative means when $b>0$.

### H3

Pass: $\Sigma$ has eigenvalues $0,2$ and unit diagonal. The displayed construction gives the required actual jointly Gaussian observation, with no independent-p-value surrogate.

### H4

Pass: the family uses exactly $0<q\leq S(1)$.

### H5

Pass: retain both original coordinates in the conditional path. Since $\rho_{12}=-1$, both residuals for the selected null are zero. With $x=u(t)$, the scores are
$$
T_1^{\,1}(t)=x,\qquad T_2^{\,1}(t)=u(q)+u(q/2)-x.
$$
For $0<t<q/2$, $x>u(q/2)$, so coordinate one qualifies for rank one; coordinate two is below $u(q)$, so rank two does not qualify. Hence the actual largest BH rank is one. For $q/2<t<q$, both scores exceed $u(q)$, so the actual largest BH rank is two. At $t=q/2$, both scores meet the rank-two threshold non-strictly, and the largest rank is two. Consequently,
$$
A_1(t)=\begin{cases}2t/q,&0<t<q/2,\\t/q,&q/2<t<q,\end{cases}
$$
and its only actual net discontinuity is at $q/2$, with left limit one and right limit $1/2$. The simultaneous events are merged into that single discontinuity. The weight of the original negative null is retained:
$$
g_1(q/2)=\exp\{-b u(q/2)-b^2/2\},\qquad
B_1=\frac12\exp\{-b u(q/2)-b^2/2\}.
$$
The residual law is deterministic, so this is already the expected charge. There are no other true-null coordinates.

### NOT

Fail: this entire family has bounded normalized budget. In fact,
$$
\frac{N^{-1}\sum_{i\in I_0}\mathbb E B_i}{\sqrt{\log(1/q)}}
=\frac{\exp\{-b u(q/2)-b^2/2\}}{4\sqrt{\log(1/q)}}
\leq\frac{1}{4\sqrt{\log(1/S(1))}}<0.185.
$$
This uses $b\geq0$ and $u(q/2)>0$; it is uniform even if $b$ depends on $q$. The numerical value is only a diagnostic; the displayed exact inequality is the failure certificate. A direct two-sided evaluation around the tied event at $q=S(1),b=0$ gave ranks one and two and $A$ limits one and $1/2$.

## Failure

NOT fails: the family's normalized positive budget is uniformly bounded by $1/(4\sqrt{\log(1/S(1))})$, so it cannot disprove existence of a universal finite constant.
