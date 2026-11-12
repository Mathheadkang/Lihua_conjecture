---
type: candidate
title: Dimension-five weak and strong quarter-mass mixture
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
round: 10
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T07:46:48.544Z'
extension_version: 0.0.4
---

## Object

Take $d=5$, $u=104$, $q=2Q(104)$, and
$$
W=\tfrac12\delta_0+\tfrac14\delta_{u/2}+\tfrac14\delta_{3u/2}.
$$
Use the product directional population $W\otimes\sigma_4$, zero residual variance, and precisely the smallest finite Gaussian-statistic contact from the supplied definition. Thus $\pi_0=1/2$. This bounded test uses the next dimension after four, with two separated nonnull means and only one quarter of the mass above $u$.

## Checks

### H1

The dimension is the integer $5\geq4$.

### H2

The displayed three-atom law is a Borel probability law on $[0,\infty)$, and its mass at zero is exactly $1/2$.

### H3

At each of its three means the conditional direction has the same uniform law $\sigma_4$, independent of the mean, by the specified product population.

### H4

The statistic is $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_5)$ and no residual noise.

### H5

The level $q=2Q(104)$ belongs to $(0,1)$ and has $Q^{-1}(q/2)=104$.

### H6

For every $r>0$, use the smallest $x\geq u$ satisfying $F_r(x)\geq2Q(x)/q$ and the prescribed zero-FDP convention if none exists. The next check shows a finite admissible cutoff exists at every such radius.

### NOT

Define $x_0$ by $Q(x_0)=Q(u)/8$. Then $x_0>u$, and Mills' bounds give
$$
\frac{Q(3u/2)}{Q(u)}
\leq\frac23(1+u^{-2})e^{-5u^2/8}<\frac18
\qquad (u=104).
$$
Thus $x_0<3u/2$. For every $r>0$, symmetry of the spherical coordinate gives $H_r(x_0-3u/2)\geq1/2$, hence
$$
F_r(x_0)\geq\tfrac14 H_r(x_0-3u/2)\geq\tfrac18
=\frac{2Q(x_0)}q.
$$
Consequently the actual first contact exists and obeys $u\leq x_r\leq x_0$ at every positive radius. Monotonicity of both tails implies
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
=q\pi_0\frac{H_r(x_r)}{Q(x_r)}
\leq q\pi_0\frac{H_r(u)}{Q(x_0)}.
$$
Gaussian radial-directional decomposition gives $\mathbb E H_R(u)=Q(u)$ exactly. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}\leq8q\pi_0.
$$
Here $M_5=1/(2\sqrt3)$, so the proposed coefficient is
$$
2+\frac{2}{\sqrt3}(1+104^{-2})\log312>8.
$$
For an exact comparison, $\log312>\log256=8\log2>16/3>3\sqrt3$; the strict inequality $\log2>2/3$ follows from its positive artanh series. Thus the displayed FDR upper bound is already strictly below the proposed right-hand side, even before its positive additive term. NOT fails.

## Failure

NOT fails first: the strong quarter-mass atom supplies a radius-independent admissible cutoff, giving FDR at most $8q\pi_0$, below the dimension-five target coefficient.
