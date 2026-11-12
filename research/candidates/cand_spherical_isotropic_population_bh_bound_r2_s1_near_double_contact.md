---
type: candidate
title: Near-simultaneous births of positive-null and zero-null spherical contacts
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
slot: 1
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-04T23:55:12.818Z'
extension_version: 0.0.4
---

## Object

Take zero residual variance, dimension $d=4$, and
$$
u=104,\qquad q=2Q(104),\qquad
\mu_* =\frac{3}{26},\qquad \varepsilon=\frac{3}{250000},\qquad
W=(1-\varepsilon)\delta_0+\varepsilon\delta_{\mu_*}.
$$
Let $Z\sim N(0,I_4)$ and use the product population $W(d\mu)\sigma_3(dv)$ with $T_{\mu,v}=\mu+v^\top Z$. Use the target's smallest finite admissible cutoff and its no-contact convention.

This tests nearly simultaneous births of two local contact branches, rather than just the zero or one null-mass endpoints. A short, one-thread double-precision diagnostic using the exact $d=4$ spherical tail gave local tangencies approximately at $(r,x)=(104.140721254675,104.126318767272)$ and $(104.140736232667,104.241732980028)$. Their FDPs were approximately $0.9998377425$ and $0$, respectively; absolute log-contact residuals were below $3\times10^{-10}$. These local optimizations are exploratory diagnostics, not a certification of all first contacts. The bound below rules out this object independently of their accuracy.

## Checks

### H1

Pass: the model uses only the shared Gaussian vector $Z$ and the statistic $\mu+v^\top Z$. Its residual variance is exactly zero.

### H2

Pass: $d=4$ is an integer satisfying $d\geq4$.

### H3

Pass: $W$ is a Borel probability measure on $[0,\infty)$, with nonnegative weights summing to one. Its true-null mass is $\pi_0=1-\varepsilon=249997/250000$.

### H4

Pass: the population is explicitly the product $W\otimes\sigma_3$. At every absolute mean, including means outside the support of $W$, choose the conditional kernel to be $\sigma_3$, so directions are uniform and independent of the absolute mean.

### H5

Pass: $q=2Q(104)$ belongs to $(0,1)$ and gives $Q^{-1}(q/2)=104$.

### H6

Pass: for every $r>0$, use the smallest finite $x\geq u$ with $F_r(x)\geq Q(x)/Q(u)$, if one exists. Set FDP to zero without a finite contact and at $r=0$. This is exactly the specified procedure; it does not select an arbitrary local branch.

### NOT

Fail: in fact this object's population FDR is less than $q$, whereas the proposed right side is greater than $2q\pi_0>q$.

Here is an explicit upper bound, independent of any first-contact optimization. Put $r_0=104.13$ and $C=4\sqrt2/(3\pi)$. The first coordinate of a uniform point of $\mathbb S^3$ has density $2\sqrt{1-z^2}/\pi$. Consequently, for $0\leq t\leq r$,
$$
H_r(t)\leq C\left(\frac{r-t}{r}\right)^{3/2},
$$
and $H_r(t)=0$ for $t\geq r$. For $u\leq x\leq r\leq r_0$, put $\delta=r-x\geq0$. Since $r\geq u$ and $x-\mu_*>0$,
$$
F_r(x)\leq \frac{C}{u^{3/2}}
\left[2\pi_0\delta^{3/2}+\varepsilon(\delta+\mu_*)^{3/2}
+\varepsilon(\delta-\mu_*)_+^{3/2}\right].
$$
The elementary Gaussian Mills inequalities give
$$
\frac{Q(x)}{Q(u)}\geq\frac{ux}{x^2+1}
\exp\left(-\frac{x^2-u^2}{2}\right).
$$
Also $(x^2+1)/(ux)\leq A:=r_0/u+u^{-2}$ and $(x^2-u^2)/2\leq r_0(r_0-u-\delta)$. Write $B=(3/(2er_0))^{3/2}$. Maximizing each nonnegative term separately over $\delta\geq0$ gives
$$
e^{-r_0\delta}\delta^{3/2}\leq B,\qquad
e^{-r_0\delta}(\delta+\mu_*)^{3/2}\leq\mu_*^{3/2},\qquad
e^{-r_0\delta}(\delta-\mu_*)_+^{3/2}\leq e^{-r_0\mu_*}B,
$$
where the middle inequality uses $\mu_*>3/(2r_0)$. Thus, uniformly for $u\leq x\leq r\leq r_0$,
$$
\frac{F_r(x)}{Q(x)/Q(u)}
\leq \frac{CA}{u^{3/2}}e^{r_0(r_0-u)}
\left[2\pi_0B+\varepsilon\mu_*^{3/2}+\varepsilon e^{-r_0\mu_*}B\right]
<0.332<1.
$$
The displayed expression evaluates to approximately $0.3310993047$; the loose upper bound $0.332$ allows ample rounding margin. Hence no finite contact with $x\leq r$ exists for $u\leq r\leq r_0$. For $r<u$, every admissible cutoff also satisfies $x>r$. Every contact with $x\geq r$ has $H_r(x)=0$ and thus zero FDP. Therefore positive FDP requires $R>r_0$.

Since FDP is a population mass ratio, it is at most one. The exact $\chi_4$ survival probability and the lower Mills inequality at $u$ imply
$$
\frac{\operatorname{FDR}_{\rm pop}}q
\leq\frac{\mathbb P(R>r_0)}{2Q(u)}
\leq
\left(1+\frac{r_0^2}{2}\right)
e^{-(r_0^2-u^2)/2}
\frac{\sqrt{2\pi}(u^2+1)}{2u}
<0.943<1.
$$
The explicit upper expression is approximately $0.9418984549$. The target's right side is at least $2q\pi_0=1.999976q$, so its conclusion holds for this object. This calculation concerns this particular finite atomic law only and establishes no uniform control of contact births or switches.

## Failure

NOT fails: the near-double-contact law has $\operatorname{FDR}_{\rm pop}<0.943q$, below the proposed right side.
