---
type: candidate
title: Vanishing true-null mass hidden among nearly null alternatives
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
slot: 5
direction: extremal
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T07:46:48.544Z'
extension_version: 0.0.4
---

## Object

For any real $u\geq104$, put $d=4$, $q=2Q(u)$, $\theta=u^{-2}$, and $\eta=e^{-u^4}$. Take
$$
W=\theta\delta_0+(1-\theta-\eta)\delta_{\eta}
   +\eta\delta_{u+u^{-1}}.
$$
Thus $\pi_0=\theta$ tends to zero polynomially while the alternative mass is nearly one. Directions are uniform and independent at each of these three means, residual variance is zero, and the cutoff is precisely the smallest finite admissible cutoff from the supplied definition. This dilution extreme has neither a large mass above $u$ nor the earlier small-total-alternative-mass premise. Its bulk of nearly null alternatives must be retained when bounding the FDP.

## Checks

### H1

The dimension $d=4$ is an integer at least four.

### H2

Since $0<\theta<1/4$ and $0<\eta<1/4$, all three weights are positive and sum to one. All support points are nonnegative, so $W$ is a Borel probability law on $[0,\infty)$, with $W(\{0\})=\theta$.

### H3

The population is explicitly $W\otimes\sigma_3$. Conditional on every absolute mean, the directions have the same uniform probability law $\sigma_3$ and are independent of that mean.

### H4

Use $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no other sampling noise. The residual variance is zero.

### H5

The choice $q=2Q(u)$ belongs to $(0,1)$ and obeys $Q^{-1}(q/2)=u\geq104$.

### H6

Use the specified smallest finite contact $x_r\geq u$ and contact identity $F_r(x_r)=2Q(x_r)/q$. At no finite contact the FDP is zero. At a finite contact it is $2\theta H_r(x_r)/F_r(x_r)$.

### NOT

The proposed violation does not occur. The following estimates hold for every $u\geq104$.

For $d=4$, $H_r$ is convex on $[0,\infty)$, including its zero extension beyond $r$: on $(0,r)$ its derivative is $-2\sqrt{1-(t/r)^2}/(\pi r)$, increasing to zero. Since $x\geq u>\eta$,
$$
H_r(x-\eta)+H_r(x+\eta)\geq2H_r(x).
$$
The combined mass at means zero and $\eta$ is $1-\eta$. Hence at every finite contact,
$$
F_r(x_r)\geq2(1-\eta)H_r(x_r),\qquad
\operatorname{FDP}_{\rm pop}(r)\leq\frac{\theta}{1-\eta}.
$$
Positive FDP requires $u\leq x_r<r$. We next bound the probability of that event.

For $r\leq2u$ and $u\leq x<r$, put $s=r-x\geq0$. The elementary spherical cap bound and Mills' lower bound give
$$
H_r(x-\eta)\leq\frac{4\sqrt2}{3\pi}
\left(\frac{s+\eta}{r}\right)^{3/2},\qquad
Q(x)\geq\frac{\phi(x)}{x+x^{-1}}.
$$
Here $x+x^{-1}\leq r(1+u^{-2})$ and $x^2-r^2=-2rs+s^2\leq-rs$. Maximizing $h^{3/2}e^{-rh/2}$ over $h\geq0$ at $h=3/r$ therefore yields
$$
\frac{H_r(x-\eta)}{Q(x)}
\leq C e^{r\eta/2}(1+u^{-2})\frac{e^{r^2/2}}{r^2},
\qquad C=\frac{8\sqrt3}{\sqrt\pi}e^{-3/2}<\frac74.
$$
Since $u\eta<u^{-3}\leq104^{-3}$, we have $C e^{r\eta/2}<2$ on this radial range.

The mass at the high mean contributes at most $\eta$, and both low-mean tails together contribute at most $2H_r(x-\eta)$. Thus
$$
F_r(x)\leq2H_r(x-\eta)+\eta.
$$
Mills' bounds also give
$$
\frac{Q(2u)}q\geq\frac{u^2}{4u^2+1}e^{-3u^2/2}
\geq\frac15e^{-3u^2/2}>\eta.
$$
At a contact in $u\leq x_r<r\leq2u$, it follows that
$$
H_r(x_r-\eta)\geq\frac{Q(x_r)}{2q},\qquad
r^2e^{-r^2/2}<4(1+u^{-2})q.
$$
The function $g(r)=r^2e^{-r^2/2}$ decreases for $r\geq u$. Since
$$
\frac{g(u)}q\geq\frac{\sqrt{2\pi}}2u^3>4(1+u^{-2}),
$$
there is a unique $b>u$ with $g(b)=4(1+u^{-2})q$. Every positive-FDP radius at most $2u$ exceeds $b$. For $R\sim\chi_4$, the exact tail gives
$$
\mathbb P(R\geq b)
=(1+b^2/2)e^{-b^2/2}
=2(1+u^{-2})(1+2/b^2)q<\frac52q.
$$
For completeness, the remaining tail is negligible without any assumption on its contacts:
$$
\frac{\mathbb P(R>2u)}q
\leq\frac{\sqrt{2\pi}}2(1+2u^2)(u+u^{-1})e^{-3u^2/2}
\leq\frac{16}{u^3}<\frac12.
$$
The second inequality uses $e^t\geq t^3/6$, $1+2u^2\leq3u^2$, and $u+u^{-1}\leq2u$. Consequently
$$
\mathbb P(\operatorname{FDP}_{\rm pop}(R)>0)<3q,
\qquad
\operatorname{FDR}_{\rm pop}<\frac{3q\theta}{1-\eta}<4q\pi_0.
$$
Finally $M_4=1/\pi$ and
$$
2+\frac4\pi(1+u^{-2})\log(3u)>4.
$$
Thus the FDR is strictly below the proposed bound, even before its positive $e^{-2u^2}$ remainder. This calculation excludes this three-atom dilution family only; it does not control arbitrary mixtures or contact switching.

## Failure

NOT fails first: nearly null alternatives dilute the true-null FDP by $\pi_0/(1-\eta)$, and a shifted cap envelope bounds the positive-FDP event by $3q$, giving FDR below $4q\pi_0$.
