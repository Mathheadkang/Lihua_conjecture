---
type: candidate
title: Exponentially small null mass with an alternative just above the cutoff edge
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
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Set $u=104$, $q=2Q(u)$, $d=7$, $p=e^{-u^2}$, and
$$
W=p\delta_0+(1-p)\delta_{u+1}.
$$
Use the product population $W(d\mu)\sigma_6(dv)$, the shared factor $Z\sim N(0,I_7)$, and $T_{\mu,v}=\mu+v^\top Z$, with no residual noise. Use exactly the smallest finite admissible Gaussian-statistic cutoff and the no-contact convention in the target definition. This tests the absence of a positive lower bound on the null proportion. The positive mean is $u+1$, below the $4u$ support boundary in the earlier strong-mean obstruction.

## Checks

### H1

The statistics have precisely the isotropic spherical population representation with zero residual variance: all sampling randomness is the stated shared Gaussian factor $Z$.

### H2

$d=7$ is an integer and $d\geq4$.

### H3

$W$ is a Borel probability measure on $[0,\infty)$, because $0<p<1$ and both displayed atoms are nonnegative. Its null mass is $W(\{0\})=p$.

### H4

The conditional directional kernel is $\sigma_6$ at every mean, including the two atoms, and is independent of $\mu$ by the stipulated product population.

### H5

The procedure and FDP are the target's largest population BH threshold, equivalently its smallest finite admissible $x\geq u$, and zero FDP when there is no finite contact. In fact a finite contact exists at every $r>0$, as established in the NOT calculation below.

### H6

$q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104\geq104$.

### NOT

This check fails by an exact upper bound. Define
$$
a=Q^{-1}\!\left(\frac{1-p}{2}Q(u)\right).
$$
Then $u<a<u+1$. For the upper inequality, translation in the Gaussian tail gives
$$
\frac{Q(u+1)}{Q(u)}\leq e^{-u-1/2}<\frac14<\frac{1-p}{2},
$$
where $p=e^{-10816}<1/4$. Since the positive mean is $u+1>a$, spherical symmetry gives, for every $r>0$,
$$
F_r(a)\geq(1-p)H_r(a-u-1)\geq\frac{1-p}{2}
=\frac{Q(a)}{Q(u)}=\frac{2Q(a)}q.
$$
Consequently $a$ is admissible and the smallest contact satisfies $u\leq x_r\leq a$. Because $F_r$ is nonincreasing,
$$
F_r(x_r)\geq F_r(a)\geq\frac{1-p}{2}.
$$
The contact identity and monotonicity of $H_r$ therefore imply
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2pH_r(x_r)}{F_r(x_r)}
\leq\frac{4p}{1-p}H_r(u).
$$
For the Gaussian radial distribution, $\mathbb E H_R(u)=Q(u)$: an independent uniform direction dotted with $Z$ is a standard Gaussian. Integrating yields
$$
\operatorname{FDR}_{\rm pop}\leq\frac{2qp}{1-p}<\frac83qp.
$$
For $d=7$, direct evaluation gives $M_7=3/(5\sqrt5)>1/4$. Since $\log(312)>1$, the proposed multiplicative coefficient obeys
$$
2+4M_7(1+u^{-2})\log(3u)>3>\frac83.
$$
Thus the object's FDR is strictly below the proposed right side, even before its positive additive term is included. The argument also works for any $u\geq104$ with the displayed choices $p=e^{-u^2}$ and $\mu=u+1$; it uses no numerical tail evaluation or unverified quadrature.

## Failure

NOT fails first: the exponentially small null mass and cutoff-edge positive mean satisfy all hypotheses, but the uniform half-mass rejection bound gives $\operatorname{FDR}_{\rm pop}<\tfrac83q\pi_0$, below the proposed bound.
