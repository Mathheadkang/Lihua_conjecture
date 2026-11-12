---
type: candidate
title: Dimension six subthreshold atom against the spherical population bound
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
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

Put $d=6$, $u=104$, $q=2Q(u)$, and
$$
W=\tfrac12\delta_0+\tfrac12\delta_{u/3},\qquad \pi_0=\tfrac12.
$$
Take the population measure $W(d\mu)\sigma_{d-1}(dv)$ and $Z\sim N(0,I_d)$, with $T_{\mu,v}(Z)=\mu+v^\top Z$ and no residual noise. Use the smallest finite admissible Gaussian-statistic cutoff from the target, with FDP zero if no finite contact exists. All logarithms below are natural.

## Checks

### H1

The dimension $d=6$ is an integer at least four.

### H2

The displayed $W$ is a Borel probability measure on $[0,\infty)$, and its atom at zero has mass exactly $\pi_0=1/2$.

### H3

The displayed statistics use the isotropic spherical population and zero residual variance: $Z$ is the only sampling randomness, and no additional observation noise is present.

### H4

By the product population measure, the direction law at each of the two absolute means is exactly $\sigma_{d-1}$, independently of the mean.

### H5

The Gaussian tail is strictly between zero and $1/2$ at $104$, so $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104\geq104$.

### H6

For each positive radius use
$$
x_r=\min\{x\geq u:F_r(x)\geq Q(x)/Q(u)\}
$$
when this set is nonempty, and $x_r=\infty$ otherwise. This is precisely the required smallest finite contact, with the required zero-FDP convention. At a finite contact the required identity is $\operatorname{FDP}_{\rm pop}(r)=q\pi_0H_r(x_r)/Q(x_r)$.

### NOT

The proposed conclusion holds for this object, so NOT fails. Here is an analytic upper bound independent of the alternative atom's location.

Write
$$
a=(d-1)/2=5/2,\qquad
c_d=\frac{\Gamma(d/2)}{\sqrt\pi\,\Gamma(a)},\qquad
C_d=\frac1{2^{d/2-1}\Gamma(d/2)},\qquad
b=\sqrt{u^2+2(d-1)\log u}.
$$
For $u\leq x<r$, the spherical coordinate density gives
$$
H_r(x)
=c_d\int_{x/r}^1(1-z^2)^{a-1}\,dz
\leq\frac{c_d2^{a-1}}a\left(\frac{r-x}{r}\right)^a.
$$
Put $s=(r^2-x^2)/2$. Since $r-x\leq s/x$ and $s^ae^{-s}\leq a^ae^{-a}$, the lower Mills inequality $Q(x)\geq\phi(x)x/(x^2+1)$ yields
$$
\frac{H_r(x)}{Q(x)}
\leq A_d(1+u^{-2})r^{-a}u^{1-a}e^{r^2/2},\qquad
A_d=\sqrt{2\pi}\,c_d2^{a-1}a^{a-1}e^{-a}.
$$
For $x\geq r$ the numerator is zero. At every radius the FDP is at most one; for $r\leq u$ it is zero. The finite-contact identity and the exact $\chi_d$ density $C_dr^{d-1}e^{-r^2/2}$ therefore imply
$$
\frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}
\leq
B_a(1+u^{-2})u^{1-a}\int_u^b r^a\,dr
+\frac{\mathbb P(R>b)}{q\pi_0},\qquad
B_a=A_dC_d=\frac{a^{a-1}e^{-a}}{\Gamma(a)}=(5/2)^{3/2}e^{-5/2}/\Gamma(5/2).
$$
Here $b<u+1$, since $2(d-1)\log u<60<209=2u+1$. Consequently
$$
(1+u^{-2})u^{1-a}\int_u^b r^a\,dr
\leq(1+u^{-2})(1+u^{-1})^a(d-1)\log u
<\frac{103}{100}(d-1)\,5.
$$
The last strict inequality uses $a\leq3$, $\log104<5$, and the exact rational inequality $(1+104^{-2})(105/104)^3<103/100$.

For the radial tail, integration after $t=r^2/2$ gives, whenever $b^2>d-2$,
$$
\mathbb P(R>b)
\leq \frac{C_db^{d-2}e^{-b^2/2}}{1-(d-2)/b^2}.
$$
Indeed, $(t+y)^{d/2-1}\leq t^{d/2-1}\exp((d/2-1)y/t)$ bounds the incomplete gamma integral. Since $q\pi_0=Q(u)$ and $e^{-(b^2-u^2)/2}=u^{-(d-1)}$, another application of the lower Mills inequality gives
$$
\frac{\mathbb P(R>b)}{q\pi_0}
\leq C_d\sqrt{2\pi}\,
\frac{(1+u^{-2})(b/u)^{d-2}}{1-(d-2)/b^2}
<\frac23\,\frac98=\frac34.
$$
In the dimensions considered here $C_d\sqrt{2\pi}\leq2/3$, and the second factor is less than $9/8$ by
$$
\frac{(1+104^{-2})(105/104)^5}{1-5/104^2}<\frac98.
$$
All displayed rational-factor comparisons are exact, rather than numerical quadrature estimates.

In this dimension $B_a<13/50$, hence
$$
\frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}
<13/50\,\frac{103}{100}(d-1)\,5+\frac34
=1489/200
<\frac{193}{25}.
$$
The elementary constant estimates used here can be certified by $e>27/10$, $e^3>20$, and $\pi>3$. For $a=5/2$, for example, $B_a^2=250/(9\pi e^5)<(13/50)^2$; for $a=2$ and $a=3$ they give $B_2<7/25$ and $B_3<9/40$ directly.

For comparison,
$$
M_5=\frac1{2\sqrt3},\qquad
M_6=\frac{\sqrt3}{2\pi},\qquad
M_7=\frac3{5\sqrt5}
$$
are all greater than $13/50$. Also $\log312>11/2$, so the proposed coefficient satisfies
$$
2+4M_d(1+u^{-2})\log(3u)
>2+4\frac{13}{50}\frac{11}{2}
=\frac{193}{25}.
$$
For an elementary certification of the logarithm comparison, use $e<11/4$ and $(11/4)^{11}<312^2$. Thus the FDR is strictly below even the $q\pi_0$ term of the target's right side, before its positive $e^{-2u^2}$ remainder. The calculation depends on $W$ only through $\pi_0=1/2$, so it also excludes every Borel mean law with that null mass at this fixed dimension and level; it supplies no bound uniform in dimension, level, or null mass.

## Failure

NOT is the first failed check: the null-only radial envelope bounds this object's FDR strictly below the proposed right side.
