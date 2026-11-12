---
type: candidate
title: Four-dimensional strong atom with half the population mass
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
round: 8
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Take $d=4$, $u=104$, $q=2Q(u)$, and
$$
W=\tfrac12\delta_0+\tfrac12\delta_{2u}.
$$
Thus $\pi_0=1/2$. At each mean take an independent uniform direction on $\mathbb S^3$, with the sole sampling randomness $Z\sim N(0,I_4)$ and statistic $T_{\mu,v}=\mu+v^\top Z$. Use exactly the smallest finite spherical population BH contact and the no-contact convention in the target definitions.

## Checks

### H1

The dimension is the integer $d=4\geq4$.

### H2

$W$ is a Borel probability law on $[0,\infty)$ and has true-null mass $W(\{0\})=1/2$.

### H3

The population law is explicitly $W\otimes\sigma_3$. Consequently the direction is uniform conditional on either mean, and independent of the mean.

### H4

There is zero residual variance: the statistic has no randomness beyond the shared Gaussian vector $Z$.

### H5

$Q(104)$ lies strictly between zero and $1/2$. Thus $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$ meets the target cutoff restriction.

### H6

For each $r>0$ use
$$
F_r(x)=H_r(x)+\tfrac12\{H_r(x-2u)+H_r(x+2u)\},\qquad
x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}.
$$
The FDP is $q\pi_0H_r(x_r)/Q(x_r)$, with the prescribed zero value if no contact exists. In fact a finite contact exists for every $r>0$: put
$$
x_0=Q^{-1}(q/8),\qquad Q(x_0)=Q(u)/4.
$$
Strict monotonicity of $Q$ gives $x_0>u$. For $a>0$, translation of the Gaussian integral gives
$$
Q(u+a)=e^{-a^2/2}\int_u^\infty e^{-at}\phi(t)\,dt
\leq e^{-ua-a^2/2}Q(u).
$$
Taking $a=u$ shows $Q(2u)<Q(u)/4$, hence $x_0<2u$. By symmetry of the continuous spherical coordinate law, $H_r(t)\geq1/2$ for every $t\leq0$. Therefore
$$
F_r(x_0)\geq\tfrac12H_r(x_0-2u)\geq\tfrac14
=\frac{2Q(x_0)}q.
$$
The specified first contact consequently satisfies $u\leq x_r\leq x_0$ at every positive radius.

### NOT

This check fails. Since $H_r$ and $Q$ are decreasing in their arguments, the preceding deterministic cutoff interval implies
$$
\frac{H_r(x_r)}{Q(x_r)}\leq\frac{H_r(u)}{Q(x_0)}.
$$
For an independent uniform direction $V$, $V^\top Z$ is standard normal. Conditional on $R=\|Z\|$, its upper tail at $u$ is $H_R(u)$; therefore $\mathbb E[H_R(u)]=Q(u)$. It follows that
$$
\operatorname{FDR}_{\rm pop}
\leq q\pi_0\frac{\mathbb E[H_R(u)]}{Q(x_0)}
=4q\pi_0.
$$
The stated gamma formula gives $M_4=1/\pi$. Using $\pi<4$ and $\log(312)>5$ gives
$$
2+4M_4(1+104^{-2})\log(312)>7.
$$
Hence the proposed right side is strictly larger than $7q\pi_0$, and in particular larger than the obtained $4q\pi_0$ upper bound. This strong-mean object does not violate the conclusion.

## Failure

NOT fails first: a universally admissible deterministic cutoff confines the first contact and gives $\operatorname{FDR}_{\rm pop}\leq4q\pi_0$, strictly below the target bound.
