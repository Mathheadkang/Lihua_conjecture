---
type: candidate
title: Dimension four with one-quarter null mass and half-threshold alternatives
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
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Take $d=4$, $u=104$, $q=2Q(u)$, and
$$
W=\tfrac14\delta_0+\tfrac34\delta_{u/2}.
$$
Use the product population $W\otimes\sigma_3$, zero residual variance, and the specified smallest finite admissible Gaussian-statistic cutoff. Thus $\pi_0=1/4$.

This tests a small null proportion outside the board's unrestricted dimension-four envelope, and an intermediate mean outside its support-and-mean-restricted subthreshold family.

## Checks

### H1

The dimension $d=4$ is an integer at least four.

### H2

The displayed two-atom $W$ is a Borel probability measure on $[0,\infty)$, with $W(\{0\})=1/4$.

### H3

Directions have the uniform probability law $\sigma_3$ independently of the mean, including at each atom of $W$.

### H4

The statistic is exactly $T_{\mu,v}(Z)=\mu+v^\top Z$ for $Z\sim N(0,I_4)$, with no residual noise.

### H5

The chosen level satisfies $0<q<1$ and $Q^{-1}(q/2)=104$.

### H6

Use the target's smallest finite contact and set FDP to zero if no finite contact exists. All quantities therefore use precisely the stipulated population BH rule.

### NOT

This check fails by an explicit admissible cutoff. Let $x_8$ be the unique solution of $Q(x_8)=Q(u)/8$. Substitution in the Gaussian integral gives
$$
\frac{Q(u+1)}{Q(u)}\leq e^{-u-1/2}<\frac18,
\qquad u<x_8<u+1.
$$
For $d=4$, the first spherical coordinate has density $2\sqrt{1-z^2}/\pi$ on $[-1,1]$. In particular,
$$
H_u(u/2)=\frac13-\frac{\sqrt3}{4\pi}>\frac3{16},
$$
where $\sqrt3<7/4$ and $\pi>3$. The same density is at most $2/\pi$, so
$$
H_u(u/2+1)>\frac3{16}-\frac{2}{\pi u}
>\frac3{16}-\frac1{156}>\frac16.
$$
For every $r\geq u$, monotonicity in the radius at positive arguments gives
$$
F_r(x_8)\geq\frac34 H_r(x_8-u/2)
\geq\frac34 H_u(u/2+1)>\frac18
=\frac{2Q(x_8)}q.
$$
Consequently a finite first contact exists there and satisfies $u\leq x_r\leq x_8$. At that contact,
$$
F_r(x_r)=\frac{Q(x_r)}{Q(u)}\geq\frac18,
\qquad
\operatorname{FDP}_{\mathrm{pop}}(r)
\leq16\pi_0H_r(u).
$$
For $r<u$, all admissible cutoffs exceed the null support, so the null FDP is zero. Since $\mathbb E H_R(u)=Q(u)$, averaging the last bound gives
$$
\operatorname{FDR}_{\mathrm{pop}}\leq8q\pi_0.
$$
Finally $M_4=1/\pi$. The elementary inequalities $e<3$, hence $e^5<243<312$, and $\pi<22/7$ imply
$$
2+4M_4(1+u^{-2})\log(3u)
>2+\frac{20}{\pi}>8.
$$
Thus this object's FDR is strictly below the proposed right side; it does not violate the conclusion. The argument is exact and does not rely on numerical tail evaluations.

## Failure

NOT fails first: a globally admissible cutoff bounds FDR by $8q\pi_0$, below the proposed coefficient in this previously unexcluded small-null, intermediate-mean example.
