---
type: candidate
title: Moderate atom barely beyond the bounded-mean edge
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
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:11:30.353Z'
extension_version: 0.0.4
---

## Object

Take $d=4$, $u=104$, $q=2Q(u)$, and
$$
\mu_* = u+u^{-2},\qquad W=\tfrac12\delta_0+\tfrac12\delta_{\mu_*}.
$$
At each absolute mean use the uniform directional law on $\mathbb S^3$, independently of the mean. Let $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$, without residual noise. Use exactly the smallest finite admissible cutoff convention in the target, including zero FDP when there is no finite contact.

This tests the support edge of the earlier bounded-mean family: the only positive mean exceeds $u$ by $u^{-2}$. The atom is moderate and is not saturated near the radii where null rejection is possible.

## Checks

### H1

Pass. $d=4$ is an integer satisfying $d\geq4$.

### H2

Pass. $W$ is a Borel probability law on $[0,\infty)$, with $\pi_0=W(\{0\})=1/2$.

### H3

Pass. The directional kernel equals the uniform law on $\mathbb S^3$ at both atoms and is independent of the absolute mean.

### H4

Pass. The sole sampling randomness is $Z\sim N(0,I_4)$, and residual variance is zero.

### H5

Pass. $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104\geq104$.

### H6

Pass. The population procedure and its no-contact convention are exactly those in the target definition.

### NOT

Fail. Define the deterministic cutoff
$$
a=u+2/u,\qquad t=a-\mu_*=2/u-u^{-2}\in(0,2/u).
$$
For $d=4$, the first directional coordinate has density
$$
f(s)=\frac2\pi\sqrt{1-s^2}\,\mathbf1_{\{|s|<1\}}\leq1.
$$
Consequently, whenever $r\geq u$,
$$
H_r(t)\geq\frac12-\frac tr>\frac12-\frac2{u^2},\qquad
F_r(a)\geq\frac12H_r(a-\mu_*)>\frac14-\frac1{u^2}>\frac15.
$$
For every $h>0$, changing variables in the Gaussian-tail integral gives
$$
Q(u+h)=e^{-uh-h^2/2}\int_u^\infty e^{-h(s-u)}\phi(s)\,ds
\leq e^{-uh-h^2/2}Q(u).
$$
Using $h=2/u$ therefore yields
$$
\frac{2Q(a)}q=\frac{Q(a)}{Q(u)}\leq e^{-2-2/u^2}<e^{-2}<\frac15<F_r(a).
$$
Thus $a$ is admissible at every $r\geq u$, so $x_r\leq a$. Monotonicity in the cutoff implies $F_r(x_r)\geq F_r(a)>1/5$, and
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq 10\pi_0H_r(u),\qquad r\geq u.
$$
For $r<u$ the null mass cannot be rejected at any $x\geq u$, so FDP is zero. Since $\mathbb E H_R(u)=Q(u)$ by the Gaussian marginal of a uniform direction independent of $Z$,
$$
\operatorname{FDR}_{\mathrm{pop}}\leq10\pi_0Q(u)=5q\pi_0.
$$
At $d=4$ one has $M_4=1/\pi$. The proposed coefficient satisfies
$$
2+\frac4\pi(1+u^{-2})\log(3u)>7
$$
because $\pi<4$ and $\log312>5$. Hence $5q\pi_0$ is strictly smaller than the proposed right side. The object does not violate the conclusion.

## Failure

NOT fails: a regional cutoff bound for all radii admitting null rejections gives $\operatorname{FDR}_{\mathrm{pop}}\leq5q\pi_0$, below the proposed bound, even with a positive-mean atom only $u^{-2}$ above the bounded-mean edge.
