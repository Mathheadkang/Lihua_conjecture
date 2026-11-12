---
type: candidate
title: Dimension-four sparse nulls with a microscopic positive mean
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
round: 6
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:07:00.541Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $m=u^{-2}=1/10816$, and
$$
W=\frac1{64}\delta_0+\frac{63}{64}\delta_m.
$$
Use the product population $W(d\mu)\sigma_3(dv)$, the statistics $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$, zero residual variance, and exactly the largest population BH threshold in the target's definition.

## Checks

### H1

The dimension $d=4$ is an integer at least four.

### H2

$W$ is a Borel probability measure on $[0,\infty)$ and $\pi_0=W(\{0\})=1/64$.

### H3

At each absolute mean the directional kernel is the same uniform measure $\sigma_3$, independent of that mean, by the stipulated product construction.

### H4

There is no additional observation noise after conditioning on $Z$; the residual variance is zero.

### H5

$q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$, satisfying the level restriction.

### H6

For every $r>0$, use $\mathcal C_r=\{x\geq u:F_r(x)\geq Q(x)/Q(u)\}$, its smallest finite member when nonempty, and FDP zero otherwise. These are exactly the prescribed cutoff and FDP conventions.

### NOT

The conclusion is not violated. In fact the following calculation gives $\operatorname{FDR}_{\rm pop}<q\pi_0$ for this object. It also holds for every Borel mean law supported on $[0,u^{-2}]$ at these $d,u$.

Put $b=(u^2+6\log u)^{1/2}$ and $k=3/2$. In dimension four the directional density on $[-r,r]$ is
$$
f_r(t)=\frac2{\pi r}\sqrt{1-(t/r)^2}.
$$
For $0\leq t\leq r$, integrating $1-(s/r)^2\leq2(r-s)/r$ gives
$$
H_r(t)\leq C\left(\frac{r-t}{r}\right)^k,
\qquad C=\frac{4\sqrt2}{3\pi}<\frac23.
$$
Consider $u\leq r\leq b$ and $x\geq u$. If $x>r+m$, then $F_r(x)=0$. Otherwise let $\delta=r+m-x\geq0$. Since all means lie in $[0,m]$, monotonicity of $H_r$ gives $F_r(x)\leq2H_r(x-m)$ and hence
$$
F_r(x)\leq 2C(\delta/r)^k.
$$
The elementary Gaussian Mills bounds give
$$
\frac{Q(x)}{Q(u)}\geq\frac{ux}{x^2+1}
\exp\{-(x^2-u^2)/2\}.
$$
Because $r+m+x\geq2u$,
$$
\frac{x^2-u^2}{2}\leq
\frac{(r+m)^2-u^2}{2}-u\delta.
$$
Also $\delta^ke^{-u\delta}\leq(k/(eu))^k$, $r\geq u$, and $(x^2+1)/(ux)\leq(b+m+u^{-1})/u$. Therefore
$$
\frac{F_r(x)Q(u)}{Q(x)}
\leq 2C\left(\frac{k}{e}\right)^k u^{-3}
e^{((b+m)^2-u^2)/2}\frac{b+m+u^{-1}}u
=2C\left(\frac{k}{e}\right)^k
e^{bm+m^2/2}\frac{b+m+u^{-1}}u.
$$
Here $\log104<5$ implies $b<u+1=105$, whence $bm+m^2/2<1/100$ and $(b+m+u^{-1})/u<53/52$. Using $e>5/2$, $(k/e)^k<3/5$, and $e^{1/100}\leq100/99$, the last display is strictly below
$$
\frac45\frac{100}{99}\frac{53}{52}<1.
$$
Thus no finite contact exists for $u\leq r\leq b$. For $r<u$ and $x\geq u$ there are no null rejections, so the FDP is zero there too.

For every radius, symmetric unimodality of $f_r$ implies that the probability of the interval $[-x-\mu,x-\mu]$ is at most that of $[-x,x]$. Consequently $F_r(x)\geq2H_r(x)$ for every nonnegative mean law; at finite contact this implies $\operatorname{FDP}_{\rm pop}\leq\pi_0$. Hence
$$
\operatorname{FDR}_{\rm pop}\leq\pi_0\mathbb P(R>b).
$$
Since $R\sim\chi_4$, its exact survival probability is $e^{-b^2/2}(1+b^2/2)$. The same lower Mills bound for $Q(u)$ yields
$$
\frac{\mathbb P(R>b)}q
\leq\sqrt{\frac\pi2}\frac{u^2+1}{u^4}
\left(1+\frac{u^2}2+3\log u\right)
<\frac32\left(1+\frac1{10000}\right)
\left(\frac12+\frac{16}{10000}\right)<1.
$$
Thus $\operatorname{FDR}_{\rm pop}<q\pi_0$, whereas the proposed right side is at least $2q\pi_0+e^{-2u^2}$.

## Failure

NOT fails first: microscopic positive means cannot create contact below the explicit radius $b$, whose exact $\chi_4$ tail is smaller than $q$.
