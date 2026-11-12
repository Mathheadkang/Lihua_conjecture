---
type: candidate
title: Pure-null dimension-five boundary above the minimum level cutoff
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
slot: 6
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Take $d=5$, $W=\delta_0$, zero residual variance, and the uniform directional kernel independent of the absolute mean. Set $u=105$ and $q=2Q(105)$. Use the prescribed smallest finite spherical population BH contact. Thus $\pi_0=1$, and the FDP equals one at each finite contact and zero otherwise.

## Checks

### H1

The dimension $d=5$ is an integer at least four.

### H2

$W=\delta_0$ is a Borel probability law on $[0,\infty)$, and $W(\{0\})=1$.

### H3

The population measure is exactly $\delta_0(d\mu)\sigma_4(dv)$, with the uniform directional kernel specified at every absolute mean, independently of that mean.

### H4

The statistics are $T_{0,v}=v^\top Z$ for $Z\sim N(0,I_5)$ and have zero residual variance.

### H5

$q=2Q(105)$ lies in $(0,1)$ and $Q^{-1}(q/2)=105\geq104$.

### H6

The object uses the prescribed smallest finite $x\geq u$ satisfying $2H_r(x)\geq Q(x)/Q(u)$, and zero FDP when there is no such finite cutoff. Continuity gives the prescribed contact identity. Since all tests are null, the FDP at a contact is exactly one.

### NOT

The following calculation applies, in fact, to this pure-null dimension-five object for every $u\geq105$. Write
$$
b^2=u^2+8\log u+4-2\log\{6(1+u^{-2})\}.
$$
For $u\leq x\leq r$, the dimension-five spherical tail has the exact form
$$
H_r(x)=\frac{(1-x/r)^2(2+x/r)}4
\leq\frac{3(r^2-x^2)^2}{16x^4}.
$$
For $x>r$ it is zero. The lower Mills bound $Q(x)\geq\phi(x)x/(x^2+1)$ and the maximum $\sup_{s\geq0}s^2e^{-s/2}=16e^{-2}$ therefore give
$$
\sup_{x\geq u}\frac{H_r(x)}{Q(x)}
\leq3\sqrt{2\pi}\,e^{-2}(1+u^{-2})u^{-3}e^{r^2/2}.
$$
Since $q\leq\sqrt{2/\pi}\,u^{-1}e^{-u^2/2}$, a finite contact, which requires $qH_r(x)/Q(x)=1$, is possible only when $r\geq b$. Consequently
$$
\operatorname{FDR}_{\rm pop}\leq\mathbb P(\chi_5\geq b).
$$
The exact radial tail is
$$
\mathbb P(\chi_5\geq b)=2Q(b)+\sqrt{\frac2\pi}e^{-b^2/2}\left(b+\frac{b^3}3\right).
$$
Using the upper Mills bound at $b$ and the lower Mills bound at $u$ yields
$$
\frac{\mathbb P(\chi_5\geq b)}q
\leq6e^{-2}(1+u^{-2})^2u^{-3}\left(\frac1b+b+\frac{b^3}3\right).
$$
For $u\geq105$, one has $u\leq b\leq2u$: the upper bound follows from $\log u\leq u^2/4$ and $u\geq2$, and the lower bound follows directly from the displayed expression for $b^2$. Hence
$$
\frac{\operatorname{FDR}_{\rm pop}}q
\leq6e^{-2}(1+u^{-2})^2\left(u^{-4}+2u^{-2}+\frac83\right)<3.
$$
For an entirely rational check of the last strict inequality, use $e^2>7$, $1+u^{-2}<1001/1000$, and $u^{-4}+2u^{-2}+8/3<267/100$; then the right side is less than $(6/7)(1001/1000)^2(267/100)<3$.

Here $M_5=1/(2\sqrt3)$, so at $u=105$ the proposed coefficient satisfies
$$
2+4M_5(1+u^{-2})\log(3u)
=2+\frac2{\sqrt3}(1+u^{-2})\log315>3.
$$
Thus this boundary object has FDR strictly below the proposed right side, even before adding $e^{-2u^2}$, and NOT fails.

## Failure

NOT fails first: the pure-null dimension-five boundary at $u=105$ has FDR below $3q$, while the proposed coefficient is greater than three.
