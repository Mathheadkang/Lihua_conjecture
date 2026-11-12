---
type: candidate
title: Dimension-eight subthreshold atom with half null mass
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
round: 5
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:53:23.256Z'
extension_version: 0.0.4
---

## Object

Take $d=8$, $u=104$, $q=2Q(104)$, and
$$
W=\frac12\delta_0+\frac12\delta_{26}.
$$
Use $Z\sim N(0,I_8)$, zero residual variance, and the product population measure $W(d\mu)\sigma_7(dv)$. Use exactly the smallest finite admissible Gaussian-statistic cutoff in the target definition, with FDP zero in the absence of a finite contact. Thus $\pi_0=1/2$.

## Checks

### H1

The dimension $d=8$ is an integer at least four. This is the next small dimension beyond the unrestricted-law, half-null envelope exclusions at dimensions four through seven on the supplied search board.

### H2

The statistic is $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_8)$ and no additional observation noise, so the residual variance is zero.

### H3

The displayed $W$ is a Borel probability measure on $[0,\infty)$, and $W(\{0\})=1/2$.

### H4

At each of the two absolute means, the conditional directional law is the same uniform measure $\sigma_7$. The product measure makes the directions independent of the mean.

### H5

Since $Q(104)\in(0,1/2)$, one has $q\in(0,1)$ and $Q^{-1}(q/2)=104\geq104$.

### H6

Use $F_r$ and $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ exactly as defined in the pack. At a finite contact the FDP is $q\pi_0H_r(x_r)/Q(x_r)$; otherwise it is zero. No different contact or cutoff is selected.

### NOT

The conclusion does not fail. Here is an analytic bound, using rational inequalities rather than a numerical contact search. Put
$$
a=\frac72,\qquad b^2=u^2+14\log u,\qquad
B=\frac{a^{a-1}e^{-a}}{\Gamma(a)}.
$$
For any $0<x<r$, the coordinate density and $1-t^2\leq2(1-t)$ give
$$
H_r(x)\leq D\,r^{-a}(r-x)^a,
\qquad D=\frac{2^{a-1}}a\frac{\Gamma(4)}{\sqrt\pi\,\Gamma(a)}.
$$
The lower Mills bound $Q(x)\geq\phi(x)x/(x^2+1)$ and
$$
e^{(x^2-r^2)/2}(r-x)^a\leq e^{-x(r-x)}(r-x)^a
\leq\left(\frac{a}{ex}\right)^a
$$
therefore imply, for every $x\geq u$,
$$
\frac{H_r(x)}{Q(x)}
\leq A(1+u^{-2})u^{1-a}r^{-a}e^{r^2/2},
\qquad A=\sqrt{2\pi}D(a/e)^a.
$$
The inequality is also true for $x\geq r$, where $H_r(x)=0$. The $\chi_8$ radial density is $Cr^7e^{-r^2/2}$ with $C=1/48$, and direct substitution gives $AC=B$. Null FDP is zero for $r\leq u$ and is at most one everywhere. Hence the actual first contact, without any branch regularity assumption, satisfies
$$
\frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}
\leq B(1+u^{-2})u^{1-a}\int_u^b r^a\,dr
+\frac{\mathbb P(R>b)}{Q(u)}.
$$
The elementary bounds
$$
\log104<\frac{14}{3},\quad \log312>\frac{11}{2},\quad
\frac bu<\frac{101}{100},\quad
\left(\frac{101}{100}\right)^{7/2}<\frac{26}{25},\quad
B<\frac{21}{100}
$$
are strict. For explicit certificates for the logarithms, use $163/60<e<11/4$ and the rational comparisons $(163/60)^{14}>104^3$ and $(11/4)^{11}<312^2$. For $B$, use
$$
B^2=\frac{33614}{225\pi e^7}
<\frac{33614}{770085}<\frac{441}{10000},
$$
where $\pi>157/50$ and $e^7>(163/60)^7>1090$. Since $u(b-u)<7\log u<98/3$ and $1+u^{-2}<10001/10000$, the integral term is strictly below
$$
\frac{21}{100}\frac{10001}{10000}\frac{98}{3}\frac{26}{25}
=\frac{44594459}{6250000}<\frac{36}{5}.
$$
The exact even-dimensional radial tail is
$$
\mathbb P(R>b)=e^{-b^2/2}\left(1+\frac{b^2}{2}+\frac{b^4}{8}+\frac{b^6}{48}\right).
$$
Again by the lower Mills bound, its ratio to $Q(u)$ is at most
$$
\sqrt{2\pi}(1+u^{-2})
\left\{u^{-6}+\frac{(b/u)^2}{2u^4}+\frac{(b/u)^4}{8u^2}+\frac{(b/u)^6}{48}\right\}.
$$
At $u=104$, replacing $b/u$ by $101/100$ makes the braces strictly less than $23/1000$, by rational cross multiplication. Since $\sqrt{2\pi}<8/3$, this ratio is strictly less than
$$
\frac83\frac{10001}{10000}\frac{23}{1000}<\frac1{16}.
$$
Consequently
$$
\operatorname{FDR}_{\rm pop}<\frac{581}{80}q\pi_0.
$$
In dimension eight, $M_8^2=500/(729\pi^2)$. The bound $\pi<22/7$ gives
$$
M_8^2>\frac{6125}{88209}>\left(\frac{13}{50}\right)^2.
$$
Thus the coefficient on $q\pi_0$ in the proposed right side is strictly greater than
$$
2+4\frac{13}{50}\frac{11}{2}=\frac{193}{25}>\frac{581}{80}.
$$
The additional $e^{-2u^2}$ is positive. Therefore this object satisfies the proposed inequality strictly. The envelope used no property of the alternative atom beyond $\pi_0=1/2$, but this check claims only the stated fixed dimension and level, not a uniform bound in dimension or level.

## Failure

NOT fails first: the dimension-eight null-only radial envelope bounds the FDR strictly below the proposed right side.
