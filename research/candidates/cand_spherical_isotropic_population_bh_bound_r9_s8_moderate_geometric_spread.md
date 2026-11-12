---
type: candidate
title: Unbounded geometric spread just beyond the bounded-mean edge
status: failed
target_asset: spherical_isotropic_population_bh_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 9
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:11:30.353Z'
extension_version: 0.0.4
---

## Object

Set $u=104$, $q=2Q(u)$, $d=4$, and
$$
W=\frac12\delta_0+\sum_{n=1}^{\infty}2^{-(n+1)}\delta_{u+n/u}.
$$
Use the product directional kernel and zero residual variance in the supplied definitions. Use their smallest finite contact and zero-FDP no-contact convention. Thus $\pi_0=1/2$. This tests the support boundary: every alternative lies just above $u$ initially, while the support is unbounded. It does not use a fixed appreciable mass at a mean of order $2u$ or larger.

## Checks

### H1

The dimension $d=4$ is an integer satisfying $d\geq4$.

### H2

The displayed $W$ is a Borel probability measure on $[0,\infty)$: all its atoms are nonnegative and $\sum_{n\geq1}2^{-(n+1)}=1/2$. Its support is unbounded and its null atom has mass $1/2$.

### H3

At every absolute mean use the same uniform probability measure on $\mathbb S^3$, independently of the mean. Hence the population measure is exactly $W\otimes\sigma_3$.

### H4

Take $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$, with no additional noise. The residual variance is zero.

### H5

Since $u=104>0$ and $Q$ is strictly decreasing, $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Use precisely the stipulated smallest finite admissible cutoff $x_r\geq u$, with FDP zero if none exists.

### NOT

This check fails. Put
$$
a=u+\frac{\log8}{u},\qquad c=\frac14-\frac1{u^2}>\frac15.
$$
The $d=4$ spherical coordinate density on $(-r,r)$ is
$$
h_r(t)=\frac{2}{\pi r}\sqrt{1-t^2/r^2}\leq\frac1r.
$$
Because $\log8<3$, for every $r\geq u$ and every alternative mean $\mu_n=u+n/u$,
$$
a-\mu_n\leq\frac{\log8-1}{u}<\frac2u,
\qquad H_r(a-\mu_n)\geq\frac12-\frac2{u^2}.
$$
For a negative tail argument the last lower bound follows from $H_r(t)\geq1/2$; for a nonnegative argument it follows by integrating $h_r\leq1/r$. Therefore $F_r(a)\geq c$ for all $r\geq u$. Directly shifting the Gaussian tail integral gives, for $b\geq0$,
$$
Q(u+b)\leq e^{-ub-b^2/2}Q(u).
$$
With $b=\log8/u$, this implies
$$
\frac{2Q(a)}q=\frac{Q(a)}{Q(u)}\leq\frac18<c\leq F_r(a).
$$
Thus a finite first contact exists with $u\leq x_r\leq a$ for every $r\geq u$. Monotonicity of $F_r$ yields $F_r(x_r)\geq c$, and monotonicity of $H_r$ yields $H_r(x_r)\leq H_r(u)$. Consequently
$$
\operatorname{FDP}_{\rm pop}(r)\leq\frac{2\pi_0}{c}H_r(u)\quad(r\geq u).
$$
For $r<u$ the null rejection mass is zero at every allowed cutoff, so the same inequality holds. Rotational invariance and $v^\top Z\sim N(0,1)$ give $\mathbb E H_R(u)=Q(u)$, hence
$$
\operatorname{FDR}_{\rm pop}\leq\frac{q\pi_0}{c}<5q\pi_0.
$$
On the other hand $M_4=1/\pi$, $\pi<4$, and $\log312>5$ imply
$$
2+4M_4(1+u^{-2})\log(3u)>7.
$$
The FDR is strictly below the proposed right side, so this object cannot violate the conclusion.

## Failure

NOT fails: even this unbounded law concentrated just above the previous support boundary has a fixed admissible cutoff and total rejection mass greater than $1/5$ on every radius where null rejection is possible, giving FDR below $5q\pi_0$.
