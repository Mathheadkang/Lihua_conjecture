---
type: candidate
title: Vanishing infinite-mean tail with finite contacts at every radius
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
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $\eta=u^{-3}$, and $\varepsilon=u^{-6}$. Let $P$ be the Pareto probability law
$$
P(d\mu)=\tfrac12\mu^{-3/2}\mathbf 1_{[1,\infty)}(\mu)\,d\mu,
\qquad P([s,\infty))=s^{-1/2}\quad(s\geq1),
$$
and take
$$
W=\tfrac12\delta_0+(\tfrac12-\varepsilon)\operatorname{Unif}(0,\eta)+\varepsilon P.
$$
At every mean use independent uniform directions on $\mathbb S^3$ and zero residual variance. Use exactly the smallest finite admissible cutoff in the supplied population BH definition.

This tests the boundary between absent and remote contacts: the arbitrarily small Pareto component makes the support unbounded and the first moment infinite, and guarantees finite contact at every positive radius, while the remaining alternative means collapse toward zero. It does not impose a fixed admissible cutoff or a strong-alternative support condition.

## Checks

### H1

The population is $W(d\mu)\sigma_3(dv)$ with $Z\sim N(0,I_4)$ and $T_{\mu,v}(Z)=\mu+v^\top Z$. There is no residual observation noise, so the required isotropic spherical population with zero residual variance is used.

### H2

The dimension $d=4$ is an integer satisfying $d\geq4$.

### H3

The three coefficients are positive and sum to one, so $W$ is a Borel probability law on $[0,\infty)$. The continuous components have no atom at zero, hence $\pi_0=W(\{0\})=1/2$. The Pareto component has infinite first moment; the target permits this.

### H4

The conditional directional kernel is $\sigma_3$ at every mean, including zero, and does not depend on the mean. Thus the directions are uniform and independent of the mean.

### H5

Use $\mathcal C_r=\{x\geq u:F_r(x)\geq Q(x)/Q(u)\}$ and $x_r=\min\mathcal C_r$ with the target's contact identity and FDP convention. In fact $\mathcal C_r$ is nonempty for every fixed $r>0$: for sufficiently large $x$, all directions at a mean $\mu\geq x+r$ reject, and therefore
$$
F_r(x)\geq\varepsilon P([x+r,\infty))
=\varepsilon(x+r)^{-1/2}>Q(x)/Q(u).
$$
The last strict inequality holds eventually because a Gaussian tail decays faster than this power. Thus all positive radii have a finite first contact, although its location need not give any null rejection.

### H6

The exact choice $q=2Q(104)$ belongs to $(0,1)$ and satisfies $Q^{-1}(q/2)=104$. No floating-point representation of this very small level is required.

### NOT

This check fails. The following exact bounds give $\operatorname{FDR}_{\mathrm{pop}}<3q/4$, whereas the proposed right side exceeds $q$.

Put
$$
b=(u^2+6\log u)^{1/2},\qquad a=b+\eta.
$$
For $d=4$, the first spherical coordinate has density $(2/\pi)\sqrt{1-s^2}$ on $[-1,1]$. Thus, for $0\leq y\leq b$,
$$
H_b(y)\leq\frac{4\sqrt2}{3\pi}\left(\frac{b-y}{b}\right)^{3/2}.
$$
For any $u\leq x\leq r\leq b$, the non-Pareto means lie in $[0,\eta]$. Monotonicity of positive spherical tails in the radius and threshold gives
$$
F_r(x)\leq2H_b(x-\eta)+\varepsilon.
$$
The Gaussian Mills bounds $Q(t)<\phi(t)/t$ and $Q(t)>\phi(t)t/(1+t^2)$, valid for $t>0$, imply
$$
\frac{Q(u)}{Q(x)}
\leq\left(\frac xu+\frac1{u^2}\right)e^{(x^2-u^2)/2}.
$$
Writing $t=a-x\geq0$ gives $e^{(x^2-u^2)/2}\leq e^{(a^2-u^2)/2}e^{-ut}$ and
$$
\sup_{t\geq0}t^{3/2}e^{-ut}=\left(\frac3{2eu}\right)^{3/2}.
$$
Consequently the non-Pareto contribution satisfies
$$
2H_b(x-\eta)\frac{Q(u)}{Q(x)}
\leq K\left(\frac ub\right)^{3/2}
\left(\frac au+\frac1{u^2}\right)e^{b\eta+\eta^2/2},
\qquad K=\frac{4\sqrt3}{\pi e^{3/2}}.
$$
Here $u=104>100$ and $\log u<5$, so
$$
\frac bu<\frac{101}{100},\qquad
\frac au+\frac1{u^2}<\frac{51}{50},\qquad
b\eta+\eta^2/2<\frac1{1000},\qquad
e^{b\eta+\eta^2/2}<\frac{101}{100}.
$$
The elementary bounds $\pi>3$ and $e>8/3$ give $K^2<9/32<9/25$, hence $K<3/5$. The displayed non-Pareto contribution is therefore strictly below
$$
\frac35\frac{51}{50}\frac{101}{100}<\frac23.
$$
The Pareto contribution, on the same range $x\leq b$, is bounded by
$$
\varepsilon\frac{Q(u)}{Q(x)}
\leq\varepsilon\left(\frac bu+\frac1{u^2}\right)
e^{(b^2-u^2)/2}
<\frac{51}{50}u^{-3}<\frac1{1000}.
$$
Thus $F_r(x)Q(u)/Q(x)<2/3+1/1000<1$ for every $u\leq x\leq r\leq b$. No such $x$ is admissible. At radii $r<u$ the interval is empty. Since every positive radius has a finite first contact by H5, the first contact satisfies $x_r>r$ whenever $r\leq b$. Consequently $H_r(x_r)=0$ and the null FDP is zero throughout this radial interval.

Always $\operatorname{FDP}_{\mathrm{pop}}\leq1$, and $R^2\sim\chi^2_4$. The exact radial tail and the lower Mills bound therefore give
$$
\operatorname{FDR}_{\mathrm{pop}}
\leq\mathbb P(R>b)
=e^{-b^2/2}(1+b^2/2),
$$
$$
\frac{\mathbb P(R>b)}q
<\frac{\sqrt{\pi/2}}2
(1+u^{-2})\left(1+\frac{2+6\log u}{u^2}\right)
<\frac23\left(\frac{101}{100}\right)^2
<\frac34.
$$
The penultimate inequality uses $\sqrt{\pi/2}<4/3$, $u>100$, and $\log u<5$. Since $\pi_0=1/2$ and $M_4>0$, the proposed right side is strictly larger than $2q\pi_0=q$. This establishes failure of NOT by exact inequalities, independently of local numerical diagnostics or contact-location optimizations.

## Failure

NOT fails first: all hypotheses hold, but the finite contacts created by the infinite-mean tail have zero null FDP below $b$, and the remaining radial tail gives $\operatorname{FDR}_{\mathrm{pop}}<3q/4<q$, below the proposed bound.
