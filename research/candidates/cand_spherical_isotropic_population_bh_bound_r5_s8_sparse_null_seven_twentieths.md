---
type: candidate
title: Sparse null mass with an alternative at seven twentieths of the initial cutoff
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
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:53:23.256Z'
extension_version: 0.0.4
---

## Object

Take the zero-residual isotropic spherical population with dimension $d=4$,
$u=104$, $q=2Q(u)$, and
$$
W=\frac1{100}\delta_0+\frac{99}{100}\delta_{7u/20}.
$$
Thus $\pi_0=1/100$ and the nonnull mean is $182/5$. At both means use the uniform spherical directional kernel, independent of the mean. Use exactly the smallest finite admissible Gaussian-statistic cutoff specified by the target, with FDP zero when no finite contact exists.

## Checks

### H1

The population statistics are $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no additional observation noise. This is the required isotropic spherical population with zero residual variance.

### H2

The dimension $d=4$ is an integer at the lower allowed endpoint.

### H3

The displayed $W$ is a Borel probability measure on $[0,\infty)$, with $W(\{0\})=1/100$.

### H4

The population law is $W\otimes\sigma_3$, so the directional kernel is uniform at every absolute mean and independent of the mean.

### H5

The cutoff is the minimum of the finite admissible set in the definition, rather than another contact or a prescribed cutoff. All bounds below apply to that minimum; no finite contact gives FDP zero.

### H6

The symbolic choice $q=2Q(104)$ belongs to $(0,1)$ and gives $Q^{-1}(q/2)=104$, exactly the required level boundary.

### NOT

This check fails: a deterministic admissible cutoff proves an upper bound of $9q\pi_0$, strictly below the proposed bound. The alternative lies below the half-cutoff support boundary of the earlier dimension-four exclusion.

Let $x_9=Q^{-1}(Q(u)/9)$. By shifting the Gaussian tail integral,
$$
Q(u+1)\leq e^{-u-1/2}Q(u)<Q(u)/9,
$$
so $u<x_9<u+1$. For every $r\geq u$,
$$
0<\frac{x_9-7u/20}{r}
<\frac{13}{20}+\frac1{104}<\frac{33}{50}.
$$
The dimension-four spherical cap satisfies
$$
H_r(t)=\frac{\arccos(t/r)-(t/r)\sqrt{1-(t/r)^2}}{\pi}
\quad (0\leq t\leq r).
$$
Here is an exact rational lower bound, without a floating-point cap evaluation. Put $z=33/50$, $a=8499/10000$, and $b=7513/10000$. Direct rational arithmetic gives
$$
1-\frac{a^2}{2}+\frac{a^4}{24}-\frac{a^6}{720}>z,
\qquad b^2>1-z^2.
$$
The first displayed polynomial is a lower bound for $\cos(a)$, so $\arccos(z)>a$. Consequently, using $\pi<22/7$,
$$
H_1(z)>
\frac7{22}(a-zb)
=\frac{1239147}{11000000},
\qquad
\frac{99}{100}\frac{1239147}{11000000}>\frac19.
$$
Thus for every $r\geq u$,
$$
F_r(x_9)\geq\frac{99}{100}H_r(x_9-7u/20)
>\frac19=\frac{2Q(x_9)}q.
$$
The actual first contact therefore exists and obeys $u\leq x_r\leq x_9$ on this radial range. For $r\leq u$, its null rejection mass is zero, whether or not contact exists. For $r>u$, monotonicity of $H_r$ and $Q$ gives
$$
\operatorname{FDP}_{\rm pop}(r)
=q\pi_0\frac{H_r(x_r)}{Q(x_r)}
\leq9q\pi_0\frac{H_r(u)}{Q(u)}.
$$
The Gaussian marginal identity $\mathbb E H_R(u)=Q(u)$ then yields
$$
\operatorname{FDR}_{\rm pop}\leq9q\pi_0.
$$
At $d=4$, the target constant is $M_4=1/\pi$. Since $\log312>11/2$ and $\pi<22/7$, its coefficient satisfies
$$
2+\frac4\pi(1+104^{-2})\log312
>2+\frac{22}{\pi}>9.
$$
The target right side is strictly larger than $9q\pi_0$, even before its positive additive remainder. Thus this object does not violate the conclusion.

## Failure

NOT fails first: the alternative at $7u/20$ supplies a uniform admissible cutoff and proves $\operatorname{FDR}_{\rm pop}\leq9q\pi_0$, below the proposed bound.
