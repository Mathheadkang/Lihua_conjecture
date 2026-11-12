---
type: candidate
title: First BH contact exactly at the null support edge with interior null mass
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
round: 2
slot: 6
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-04T23:55:12.818Z'
extension_version: 0.0.4
---

## Object

Let $u=104$, $q=2Q(u)$, and $d=4$. Define
$$
r_0=Q^{-1}(Q(u)/2),\qquad x_1=Q^{-1}(Q(u)/4),\qquad \mu_*=2r_0,
\qquad W=\tfrac12\delta_0+\tfrac12\delta_{\mu_*}.
$$
Use exactly the product directional population and the first finite contact convention in the target. In particular, $\pi_0=1/2$. There is no residual observation noise. The feature being tested is an equality contact at $x=r=r_0$: the first BH contact is exactly the support edge of the null statistic, while both null and alternative population masses are positive.

For reproducibility, a one-thread SciPy diagnostic using `log_ndtr` and `ndtri_exp` gives $r_0\simeq104.00666404723398$, $x_1\simeq104.01332766758675$, $\mu_*\simeq208.01332809446797$, and $\log q\simeq-5412.870274686048$. The checks below use exact inequalities rather than floating-point values of $q$.

## Checks

### H1

The observation is $T_{\mu,v}(Z)=\mu+v^\top Z$ for $Z\sim N(0,I_4)$, with no additional noise. This is the target's spherical directional population with zero residual variance.

### H2

The dimension $d=4$ is an integer in the permitted range.

### H3

$W$ is a two-atom Borel probability measure on $[0,\infty)$, and its null mass is exactly $W(\{0\})=1/2$ because $\mu_*>0$.

### H4

The population measure is $W\otimes\sigma_3$, with directional kernel $\sigma_3$ at each absolute mean. Thus the directions are uniform and independent of the absolute mean.

### H5

The procedure uses the smallest finite cutoff satisfying $F_r(x)\ge Q(x)/Q(u)$, and FDP zero if no such cutoff exists. In fact a finite contact exists for every $r>0$ here. To see this, first note that
$$
Q(2r_0)\le e^{-3r_0^2/2}Q(r_0)<\tfrac12Q(r_0)=Q(x_1),
$$
where the first inequality follows by translating the Gaussian tail integral by $r_0$. Hence $x_1<2r_0=\mu_*$. For every $r>0$, symmetry gives $H_r(x_1-\mu_*)\ge1/2$, so
$$
F_r(x_1)\ge\tfrac12 H_r(x_1-\mu_*)\ge\tfrac14
=\frac{Q(x_1)}{Q(u)}.
$$
Consequently the target's first contact exists and $u\le x_r\le x_1$ for every $r>0$.

The intended boundary equality is exact. At $r=r_0$ and $u\le x\le r_0$, the alternative is always rejected: $H_{r_0}(x-2r_0)=1$ and $H_{r_0}(x+2r_0)=0$. Thus
$$
F_{r_0}(x)=\tfrac12+H_{r_0}(x),\qquad
F_{r_0}(r_0)=\tfrac12=\frac{Q(r_0)}{Q(u)}.
$$
For $d=4$ the spherical projection density on $(-r_0,r_0)$ is
$$
f_{r_0}(x)=\frac{2}{\pi r_0}\sqrt{1-(x/r_0)^2}\le\frac{2}{\pi r_0}.
$$
Define $A(x)=Q(x)/Q(u)-1/2-H_{r_0}(x)$. On $[u,r_0)$,
$$
A'(x)=-\frac{\phi(x)}{Q(u)}+f_{r_0}(x)
\le-\frac{\phi(r_0)}{Q(u)}+\frac{2}{\pi r_0}
<-\frac{r_0}{2}+\frac{2}{\pi r_0}<0,
$$
using the strict Gaussian Mills inequality $\phi(r_0)/Q(r_0)>r_0$ and $Q(r_0)=Q(u)/2$. Since $A(r_0)=0$, one has $A(x)>0$ for $u\le x<r_0$. There is no earlier contact, so $x_{r_0}=r_0$ and its null rejection mass is exactly zero.

### H6

$q=2Q(104)$ belongs to $(0,1)$, and $Q^{-1}(q/2)=104$. This is the permitted endpoint of the level restriction.

### NOT

Fail. The uniform cutoff bound in H5 yields, for every $r>0$,
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
=q\pi_0\frac{H_r(x_r)}{Q(x_r)}
\le q\pi_0\frac{H_r(u)}{Q(x_1)}.
$$
For $R=\|Z\|_2$, the spherical-Gaussian marginal identity gives $\mathbb E H_R(u)=Q(u)$. Indeed, an independent uniform direction $V$ satisfies $V^\top Z\sim N(0,1)$, and conditioning on $R$ gives the tail $H_R(u)$. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}\le q\pi_0\frac{Q(u)}{Q(x_1)}=4q\pi_0.
$$
Here $M_4=1/\pi$, and the coefficient in the proposed bound is
$$
2+\frac4\pi(1+104^{-2})\log312>4
\qquad(\text{numerically }9.312894819988077).
$$
The proposed right-hand side therefore exceeds this analytic FDR upper bound, even before its positive $e^{-2u^2}$ term is added. The support-edge contact does not violate the target.

## Failure

NOT is the first failed check: an exact first contact at the null support edge exists, but the full population FDR is at most $4q\pi_0$, strictly below the proposed bound.
