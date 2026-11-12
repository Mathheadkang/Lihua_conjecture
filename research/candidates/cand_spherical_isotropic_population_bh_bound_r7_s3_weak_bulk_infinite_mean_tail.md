---
type: candidate
title: Weak bulk with a sparse infinite-mean Pareto tail
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
round: 7
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:40:00.656Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $m=1/u$, and
$$
b=\frac{Q(2u)}{10q},\qquad
\nu(d\mu)=\mathbf 1_{[1,\infty)}(\mu)\mu^{-2}\,d\mu,\qquad
W=\frac12\delta_0+\left(\frac12-b\right)\delta_m+b\nu.
$$
Use the product directional population $W\otimes\sigma_3$, zero residual variance, and exactly the stipulated smallest finite Gaussian-statistic contact, with FDP zero if it does not exist. Thus $\pi_0=1/2$. The alternative has unbounded support and infinite first moment. Its weak bulk lies at $u^{-1}$, above the microscopic ranges in the supplied board.

## Checks

### H1

The dimension is the integer $d=4\geq4$.

### H2

The law $\nu$ is a Borel probability because $\int_1^\infty\mu^{-2}\,d\mu=1$. Since $0<Q(2u)<Q(u)=q/2$, one has $0<b<1/20$, so the mixture weights are positive and sum to one. Hence $W$ is a Borel probability on $[0,\infty)$. Also $\int\mu\,\nu(d\mu)=\int_1^\infty\mu^{-1}\,d\mu=\infty$, which is allowed.

### H3

At each absolute mean, including those in the Pareto component, the conditional direction is $\sigma_3$ and is independent of the mean by the specified product measure.

### H4

Take $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$ with no additional noise, so residual variance is zero.

### H5

The value $q=2Q(104)$ belongs to $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Use $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when the set is nonempty and $x_r=\infty$ otherwise. Thus the contact identity and the no-finite-contact convention are exactly those in the target.

### NOT

This check fails: the following analytic estimate gives
$$
\operatorname{FDR}_{\rm pop}<5q\pi_0,
$$
strictly below the proposed right side.

First, the $d=4$ directional density on $[-r,r]$ is
$$
g_r(t)=\frac{2}{\pi r^2}\sqrt{r^2-t^2}.
$$
It is symmetric and nonincreasing away from zero. An interval of length $2x$ has maximum mass when centered at zero. Thus every mean $\mu\geq0$ has rejection probability at least $2H_r(x)$, whence $F_r(x)\geq2H_r(x)$ and the contact FDP is at most $\pi_0$.

For $0<t<r$, put $D=r^2-t^2$. Substituting $y=r^2-s^2$ gives
$$
H_r(t)=\frac{2}{\pi r^2}\int_t^r\sqrt{r^2-s^2}\,ds
\leq\frac{2D^{3/2}}{3\pi r^2t}.
$$
Use $Q(t)\geq\phi(t)t/(t^2+1)$ and maximize $D^{3/2}e^{-D/2}$ at $D=3$ to obtain
$$
\frac{H_r(t)}{Q(t)}
\leq A(1+t^{-2})\frac{e^{r^2/2}}{r^2},\qquad
A=\sqrt{\frac{24}{\pi e^3}}<\frac23.
$$
Indeed, $\pi>3$ and $e>8/3$ imply $A^2<27/64<4/9$. For $t>100$, the displayed ratio is therefore less than $(3/4)e^{r^2/2}/r^2$.

Suppose a contact has positive null FDP and $r\leq2u$. Necessarily $u\leq x_r<r$, and $t=x_r-m>100$. For $u\leq x\leq2u$, the two Mills inequalities imply
$$
\frac{Q(x-m)}{Q(x)}
\leq e^{xm-m^2/2}\frac{x^2+1}{x(x-m)}
\leq e^2\frac{1+u^{-2}}{1-u^{-2}}<8.
$$
For the last constant, $e<11/4$, $u>100$, and $(121/16)(10001/9999)<8$ suffice. Write $h(r)=e^{r^2/2}/r^2$. The weak part has means in $[0,m]$, whereas the entire Pareto part has mass $b$, so
$$
F_r(x)\leq2H_r(x-m)+b\leq12h(r)Q(x)+b.
$$
Also $b\leq Q(x)/(10q)$ for $x\leq2u$. The contact identity then implies
$$
\frac{2Q(x_r)}q\leq12h(r)Q(x_r)+\frac{Q(x_r)}{10q},
\qquad h(r)\geq\frac{19}{120q}.
$$
There is a unique $s>u$ with $h(s)=19/(120q)$: $h$ is strictly increasing above $u$, diverges, and
$$
qh(u)\leq\frac{\sqrt{2/\pi}}{u^3}<\frac{19}{120}.
$$
Thus positive null FDP at $r\leq2u$ requires $r\geq s$. Since $R\sim\chi_4$,
$$
\mathbb P(R\geq s)
=(1+s^2/2)e^{-s^2/2}
=\frac{120q}{19}\left(\frac1{s^2}+\frac12\right)
<\frac{10q}{3}.
$$
The rational comparison is $(120/19)(1/2+1/10000)<10/3$. Moreover,
$$
\frac{\mathbb P(R>2u)}q
\leq\frac{\sqrt{2\pi}(u^2+1)(1+2u^2)}{2u}e^{-3u^2/2}
<9u^3e^{-3u^2/2}<1.
$$
For the last inequality, $3u^2/2>6\log u$ at $u=104$, which bounds the preceding expression by $9/u^3<1$. Combining the two radial events with the conditional FDP bound gives
$$
\operatorname{FDR}_{\rm pop}
\leq\pi_0\{\mathbb P(R\geq s)+\mathbb P(R>2u)\}
<\frac{13}{3}q\pi_0<5q\pi_0.
$$
Finally $M_4=1/\pi$, and the target coefficient exceeds $7$: $\pi<4$ and $\log312>5$, the latter following from $e^5<3^5=243<312$. Thus the target right side exceeds $7q\pi_0$ even before its positive additive term. NOT fails.

## Failure

NOT fails first: the weak-bulk, infinite-mean mixture obeys the explicit radial exclusion $\operatorname{FDR}_{\rm pop}<5q\pi_0$, below the target right side.
