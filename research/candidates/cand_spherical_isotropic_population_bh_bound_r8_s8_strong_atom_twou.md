---
type: candidate
title: Half-null mixture with a strong atom at twice the baseline cutoff
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
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$ and
$$
W=\tfrac12\delta_0+\tfrac12\delta_{2u},\qquad \pi_0=\tfrac12.
$$
At both means use independent uniform directions on $\mathbb S^3$, with $Z\sim N(0,I_4)$ and no residual noise. Use precisely the target's smallest finite contact and zero FDP in the absence of a contact. This tests means above the baseline cutoff, outside the support-restricted monotone-transport family.

## Checks

### H1

The dimension is the integer $d=4\geq4$.

### H2

$W$ is a Borel probability law on $[0,\infty)$, and its mass at zero is $\pi_0=1/2$.

### H3

The population measure is exactly $W\otimes\sigma_3$, so directions are uniform and independent of the absolute mean at every mean in the support.

### H4

The statistic is $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and zero residual variance.

### H5

The choice $q=2Q(104)$ lies in $(0,1)$ and gives $Q^{-1}(q/2)=104\geq104$.

### H6

For every $r>0$ the rule is exactly the smallest $x\geq u$ with $F_r(x)\geq2Q(x)/q$, with the specified no-contact convention.

### NOT

This check fails by a uniform positive-denominator bound, without any monotonicity assertion in $r$.

Let $v=Q^{-1}(q/8)=Q^{-1}(Q(u)/4)$. Then $u<v<2u$: the upper inequality follows from
$$
Q(2u)=\int_u^\infty\phi(s+u)\,ds
\leq e^{-3u^2/2}Q(u)<Q(u)/4.
$$
For every $r>0$ and $x\leq v$, the strong component has
$$
H_r(x-2u)\geq\tfrac12,
$$
by symmetry, since $x-2u<0$. Thus $F_r(x)\geq1/4$. In particular,
$$
F_r(v)\geq\tfrac14=2Q(v)/q,
$$
so a finite contact exists for every $r>0$ and $u\leq x_r\leq v$. At that contact,
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq8\pi_0H_r(u).
$$
Averaging over $R=\|Z\|$ gives $\mathbb E H_R(u)=Q(u)$: for an independent uniform direction $V$, $V^\top Z$ has the standard normal law. Consequently
$$
\operatorname{FDR}_{\rm pop}\leq8\pi_0Q(u)=4q\pi_0.
$$
Here $M_4=1/\pi$. Since $\pi<4$ and $\log(312)>5$, the proposed coefficient satisfies
$$
2+4M_4(1+u^{-2})\log(3u)>7>4.
$$
The proposed right side is therefore strictly larger than the displayed FDR upper bound. The strong atom does not violate the target.

## Failure

NOT fails: a strong-mean mass of one half keeps the contact denominator at least one quarter and yields $\operatorname{FDR}_{\rm pop}\leq4q\pi_0$, below the target bound.
