---
type: candidate
title: Sparse null mass with a strong spherical alternative
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
slot: 4
direction: known_counterexamples
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Set $u=104$, $q=2Q(u)$, $d=8$, $\pi_0=1/1024$, $a=1-\pi_0=1023/1024$, and
$$
W=\pi_0\delta_0+a\delta_{2u}.
$$
Take $Z\sim N(0,I_8)$ and the test population $W\otimes\sigma_7$, with statistic $T_{\mu,v}(Z)=\mu+v^\top Z$ and no residual noise. Use the smallest finite admissible Gaussian cutoff, with zero FDP if none exists, exactly as in the target's definition. This sparse-null configuration tests whether an exceptionally small null mass can expose inflation missed by the board's fixed strong-mean parameter pairs.

## Checks

### H1

The statistics are precisely $\mu+v^\top Z$ with $Z\sim N(0,I_8)$ and no additional random term, so the stipulated spherical model has zero residual variance.

### H2

The dimension $d=8$ is an integer and satisfies $d\geq4$.

### H3

The measure $W$ is a Borel probability law on $[0,\infty)$: its positive weights sum to one and its support is $\{0,208\}$. Its exact null mass is $W(\{0\})=\pi_0=1/1024$.

### H4

The population measure is $W\otimes\sigma_7$. Specify its conditional directional kernel to be $\sigma_7$ at every absolute mean, including outside the support of $W$. Thus directions are uniform and independent of the mean as required.

### H5

For every $r>0$ use
$$
\mathcal C_r=\{x\geq u:F_r(x)\geq2Q(x)/q\},\qquad
x_r=\min\mathcal C_r
$$
when this set is nonempty, and use the target's no-contact convention otherwise. At finite contact use $\operatorname{FDP}_{\mathrm{pop}}(r)=q\pi_0H_r(x_r)/Q(x_r)$. This is exactly the prescribed procedure.

### H6

Since $u=104>0$, $q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$, so the level restriction holds exactly.

### NOT

The proposed conclusion does not fail. Define the deterministic cutoff
$$
b=Q^{-1}\!\left(\frac a2Q(u)\right).
$$
It satisfies $u<b<2u$. For the upper inequality, shifting the Gaussian tail variable gives
$$
\frac{Q(2u)}{Q(u)}
=\frac{\int_u^\infty e^{-ut-u^2/2}\phi(t)\,dt}
{\int_u^\infty\phi(t)\,dt}
\leq e^{-3u^2/2}<\frac14<\frac a2,
$$
where $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$. Monotonicity of $Q$ gives $b<2u$.

For every $r>0$, spherical symmetry and $b-2u<0$ imply $H_r(b-2u)\geq1/2$. Consequently,
$$
F_r(b)\geq aH_r(b-2u)\geq\frac a2
=\frac{2Q(b)}q.
$$
Thus a finite contact exists at every positive radius and $u\leq x_r\leq b$. Monotonicity of the two tails then yields
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
\leq\frac{q\pi_0H_r(u)}{Q(b)}
=\frac{2q\pi_0}{a}\frac{H_r(u)}{Q(u)}.
$$
For $R=\|Z\|_2$, the Gaussian marginal identity $\mathbb E H_R(u)=Q(u)$ follows by averaging over an independent uniform direction $V$: conditionally on any fixed $V$, $V^\top Z\sim N(0,1)$. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}
\leq\frac2a q\pi_0
=\frac{2048}{1023}q\pi_0
<3q\pi_0.
$$
The dimension-eight constant is exactly
$$
M_8=\frac{10\sqrt5}{27\pi}>\frac7{27}>\frac14,
$$
where the first strict inequality uses $\sqrt5>11/5$ and $\pi<22/7$. Since $\log(3u)=\log312>1$, the coefficient in the proposed bound satisfies
$$
2+4M_8(1+u^{-2})\log(3u)>3.
$$
Hence this object's FDR is strictly below the proposed right side, even without its positive additive term. Every comparison is analytic; no floating-point tail value is used.

## Failure

NOT is the first failing check: a cutoff admissible at every radius gives $\operatorname{FDR}_{\mathrm{pop}}\leq(2048/1023)q\pi_0<3q\pi_0$, below the proposed bound.
