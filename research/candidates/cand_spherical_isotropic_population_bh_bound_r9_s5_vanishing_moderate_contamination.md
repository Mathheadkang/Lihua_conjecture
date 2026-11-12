---
type: candidate
title: Vanishing contamination at a mean just above the bounded-mean regime
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
round: 9
slot: 5
direction: extremal
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:11:30.353Z'
extension_version: 0.0.4
---

## Object

For every real $u\geq104$, put $d=4$, $q=2Q(u)$, $\varepsilon=e^{-u^4}$, and
$$
W=(1-\varepsilon)\delta_0+\varepsilon\delta_{u+u^{-1}}.
$$
At both means use independent uniform directions on $\mathbb S^3$ and zero residual variance. Use exactly the stipulated smallest finite contact, with FDP zero when there is no contact. The alternative mean exceeds $u$, so the board's support-restricted monotone-transport exclusion does not apply to this object. Its alternative mass vanishes much faster than the Gaussian tail, unlike the appreciable strong-signal masses of the preceding extremal tests.

## Checks

### H1

$d=4$ is an integer at least four.

### H2

$W$ is a Borel probability law on $[0,\infty)$, with $\pi_0=1-\varepsilon>1/2$.

### H3

The population index law is $W\otimes\sigma_3$, so every conditional directional law is uniform and independent of the mean.

### H4

The statistics are $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no residual noise.

### H5

$q=2Q(u)\in(0,1)$ and $Q^{-1}(q/2)=u\geq104$.

### H6

The finite cutoff is $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$, as specified. At a finite contact $F_r(x_r)=2Q(x_r)/q$, and the FDP is $2\pi_0H_r(x_r)/F_r(x_r)\leq1$. No-contact radii have FDP zero.

### NOT

This check fails. A rare-contamination argument, independent of the alternative mean, gives $\operatorname{FDR}_{\rm pop}<3q$, which lies strictly below the proposed right side for this object.

First, Mills' bounds imply
$$
\frac{Q(2u)}q
\geq\frac{u^2}{4u^2+1}e^{-3u^2/2}
\geq\frac15e^{-3u^2/2}
>e^{-u^4}=\varepsilon.
$$
The final inequality follows from $u^4-3u^2/2>\log5$ for $u\geq104$. For all $r,x$, the alternative rejection probability is at most one, hence
$$
F_r(x)\leq2H_r(x)+\varepsilon.
$$
Suppose $r\leq2u$ and a finite contact has positive FDP. Then $u\leq x_r<r\leq2u$, and the contact identity yields
$$
2H_r(x_r)
\geq\frac{2Q(x_r)}q-\varepsilon
\geq\frac{Q(x_r)}q,
\qquad
\frac{H_r(x_r)}{Q(x_r)}\geq\frac1{2q}.
$$

For $d=4$ and $u\leq x<r$, set $h=r-x$. The spherical coordinate density gives
$$
H_r(x)=\frac2\pi\int_{x/r}^1\sqrt{1-t^2}\,dt
\leq\frac{4\sqrt2}{3\pi}(h/r)^{3/2}.
$$
Combining this with $Q(x)\geq\phi(x)x/(x^2+1)$ and $x+x^{-1}\leq r(1+u^{-2})$ gives
$$
\frac{H_r(x)}{Q(x)}
\leq\frac8{3\sqrt\pi}(1+u^{-2})
\frac{h^{3/2}}{r^{1/2}}e^{r^2/2}e^{-rh+h^2/2}.
$$
Since $0<h<r$, the last exponential is at most $e^{-rh/2}$. Maximizing $h^{3/2}e^{-rh/2}$ over $h\geq0$ gives $(3/r)^{3/2}e^{-3/2}$. Therefore
$$
\frac{H_r(x)}{Q(x)}
\leq C(1+u^{-2})\frac{e^{r^2/2}}{r^2},
\qquad
C=\frac{8\sqrt3}{\sqrt\pi}e^{-3/2}<2.
$$
For the stated strict bound, $C^2=192/(\pi e^3)<4$ follows already from $\pi>3$ and $e^3>16$.

Consequently every positive-FDP radius at most $2u$ satisfies
$$
r^2e^{-r^2/2}<4(1+u^{-2})q.
$$
The function $g(r)=r^2e^{-r^2/2}$ is strictly decreasing for $r\geq u$. Moreover, by the upper Mills bound,
$$
g(u)/q\geq(\sqrt{2\pi}/2)u^3>4(1+u^{-2}).
$$
Thus there is a unique $b>u$ with $g(b)=4(1+u^{-2})q$, and every such radius exceeds $b$. The exact $\chi_4$ tail is
$$
\mathbb P(R\geq b)=(1+b^2/2)e^{-b^2/2}
\leq2(1+u^{-2})(1+2u^{-2})q<\frac52q.
$$
For the radii above $2u$, Mills' lower bound also gives
$$
\frac{\mathbb P(R>2u)}{Q(u)}
\leq18u^3e^{-3u^2/2}<\frac{32}{u^3}<1.
$$
Here $\mathbb P(R>2u)=(1+2u^2)e^{-2u^2}$, $\sqrt{2\pi}<3$, and $e^{3u^2/2}>(3u^2/2)^3/6=9u^6/16$ justify the displayed inequalities. Since the FDP never exceeds one,
$$
\operatorname{FDR}_{\rm pop}
\leq\mathbb P(R\geq b)+\mathbb P(R>2u)
<\frac52q+Q(u)=3q.
$$
Finally $M_4=1/\pi$, $\pi<4$, and $\log(3u)>5$ imply
$$
2+4M_4(1+u^{-2})\log(3u)>7.
$$
Together with $\pi_0>1/2$, this gives
$$
\operatorname{FDR}_{\rm pop}<3q
<7q\pi_0
<q\pi_0\{2+4M_4(1+u^{-2})\log(3u)\}+e^{-2u^2}.
$$
This excludes the displayed vanishing-contamination family only. It does not control arbitrary mixture masses, dimensions, or global switches of the first contact.

## Failure

NOT fails first: a uniform spherical-cap likelihood bound makes positive-FDP radii rare enough that this vanishing moderate-signal contamination has FDR below $3q$, strictly below the target bound.
