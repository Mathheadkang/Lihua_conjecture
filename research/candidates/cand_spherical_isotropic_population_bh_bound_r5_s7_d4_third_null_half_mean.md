---
type: candidate
title: Dimension four with one-third null mass and a half-cutoff alternative
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
round: 5
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:53:23.256Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, and
$$
W=\frac13\delta_0+\frac23\delta_{u/2}.
$$
Thus $\pi_0=1/3$. Give each mean the independent uniform directional law on $\mathbb S^3$, take $Z\sim N(0,I_4)$, and use $T_{\mu,v}=\mu+v^\top Z$ with zero residual variance. Use exactly the prescribed smallest finite admissible cutoff, with zero FDP when there is no finite contact.

This smallest-dimension mixture has null mass strictly between the board's $1/4$ upper boundary for its half-cutoff exclusion and its $1/2$ lower boundary for its unrestricted null-envelope exclusion.

## Checks

### H1

Pass. The displayed Gaussian factor and statistics specify the isotropic spherical directional population with zero residual variance.

### H2

Pass. The dimension is the allowed smallest integer $d=4$.

### H3

Pass. $W$ is a Borel probability measure on $[0,\infty)$, and its mass at zero is $\pi_0=1/3$.

### H4

Pass. The population measure is $W\otimes\sigma_3$, so conditional directions are uniform at each of the two absolute means and independent of the mean.

### H5

Pass. $q=2Q(104)$ lies strictly between zero and one and $Q^{-1}(q/2)=104$.

### H6

Pass. The cutoff and FDP follow the definition in the pack, including the no-contact convention.

### NOT

Fail. A deterministic admissible cutoff yields the strict upper bound below.

Define $x_9$ by $Q(x_9)=Q(u)/9$. Since
$$
\frac{Q(u+1)}{Q(u)}
\leq e^{-u-1/2}<\frac19,
$$
one has $u<x_9<u+1$. For $d=4$ the first coordinate has density
$$
f_4(s)=\frac2\pi\sqrt{1-s^2}\,\mathbf1_{(-1,1)}(s),
$$
and hence
$$
H_u(u/2)=\frac13-\frac{\sqrt3}{4\pi}>\frac3{16}.
$$
The last strict inequality follows from $\sqrt3<7/4$ and $\pi>3$. The density bound $f_4\leq2/\pi<2/3$ gives
$$
H_u(u/2+1)>\frac3{16}-\frac1{156}>\frac16.
$$
For every $r\geq u$, radial monotonicity of a cap at a positive threshold therefore gives
$$
H_r(x_9-u/2)\geq H_u(x_9-u/2)>\frac16,
$$
and consequently
$$
F_r(x_9)\geq\frac23H_r(x_9-u/2)>\frac19
=\frac{2Q(x_9)}q.
$$
Thus a finite contact exists and its smallest cutoff satisfies $x_r\leq x_9$ whenever $r\geq u$. At such a radius,
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{q\pi_0H_r(x_r)}{Q(x_r)}
\leq\frac{9q\pi_0H_r(u)}{Q(u)}.
$$
For $r<u$, the FDP is zero since $x_r\geq u>r$ at any finite contact. The Gaussian marginal identity $\mathbb E[H_R(u)]=Q(u)$ now implies
$$
\operatorname{FDR}_{\rm pop}\leq9q\pi_0=3q.
$$
Here $M_4=1/\pi$. The proposed multiplicative coefficient is strictly greater than nine, because $\log312>11/2$ and $\pi<22/7$ imply
$$
2+\frac4\pi(1+104^{-2})\log312
>2+\frac{22}\pi>9.
$$
The proposed right side, including its positive exponential term, is therefore strictly greater than $9q\pi_0$, so the object does not violate the conclusion. The same cutoff calculation would exclude every law $p\delta_0+(1-p)\nu$ with $0<p\leq1/3$, $d=4$, $u\geq104$, and $\nu([u/2,\infty))=1$.

## Failure

NOT fails first: the half-cutoff alternative mass makes $x_9$ globally admissible for $r\geq u$, giving $\operatorname{FDR}_{\rm pop}\leq9q\pi_0$ strictly below the proposed bound.
