---
type: candidate
title: >-
  Infinite-mean Lomax alternatives beyond the microscopic concentration
  exclusion
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
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:40:00.656Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, and $a=e^{-u^2}$. Let $\nu_a$ be the Lomax probability law on $[0,\infty)$ with density $a/(a+\mu)^2$ and survival function $\nu_a((t,\infty))=a/(a+t)$. Take
$$
W=\tfrac12\delta_0+\tfrac12\nu_a,\qquad \pi_0=\tfrac12.
$$
Use the product population $W(d\mu)\sigma_3(dv)$ and statistics $T_{\mu,v}=\mu+v^\top Z$, where $Z\sim N(0,I_4)$, with the prescribed smallest finite contact and no-contact convention. The alternative law has infinite first moment.

## Checks

### H1

The object is the isotropic spherical directional population, with no noise beyond the shared Gaussian vector. Thus residual variance is zero.

### H2

The dimension $d=4$ is an integer satisfying $d\geq4$.

### H3

The density integrates to one, since $\int_0^\infty a/(a+\mu)^2\,d\mu=1$. Therefore $W$ is a Borel probability measure on $[0,\infty)$ with the stated null mass. Its support is unbounded. Moreover,
$$
\int_0^\infty \nu_a((t,\infty))\,dt
=\int_0^\infty\frac{a}{a+t}\,dt=\infty.
$$

### H4

The product population specifies the same uniform directional kernel $\sigma_3$ at every absolute mean, independently of that mean.

### H5

For each $r>0$ use exactly $\mathcal C_r=\{x\geq u:F_r(x)\geq2Q(x)/q\}$, $x_r=\min\mathcal C_r$ when it is nonempty, and FDP zero otherwise. No alternative contact selection is introduced.

### H6

The strictly positive Gaussian survival probability gives $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### NOT

The conclusion holds with the stronger estimate $\operatorname{FDR}_{\rm pop}<6q\pi_0$.

Here are explicit estimates. Write $\delta=u^{-2}$ and $\varepsilon=W((\delta,\infty))$. Then
$$
\varepsilon=\frac{a}{2(a+\delta)}<u^2e^{-u^2},\qquad
F_r(x)\leq2H_r(x-\delta)+\varepsilon.
$$
The last inequality splits the means at $\delta$; the rejection probability at a mean above $\delta$ is at most one.

For $2\leq t\leq r$, the dimension-four coordinate density and the lower Mills inequality give
$$
H_r(t)=\frac2{\pi r^2}\int_t^r\sqrt{r^2-y^2}\,dy
\leq\frac{4\sqrt2}{3\pi}\left(\frac{r-t}{r}\right)^{3/2},
\qquad
\frac1{Q(t)}<\sqrt{2\pi}\,(t+t^{-1})e^{t^2/2}.
$$
Put $h=r-t$ and $z=rh$. Since $t+t^{-1}\leq5r/4$ and $t^2/2\leq r^2/2-rh/2$,
$$
\frac{H_r(t)}{Q(t)}
\leq\frac{10}{3\sqrt\pi}\frac{e^{r^2/2}}{r^2}
\sup_{z\geq0}z^{3/2}e^{-z/2}
=\frac{10}{3\sqrt\pi}\left(\frac3e\right)^{3/2}
\frac{e^{r^2/2}}{r^2}
<\frac52\frac{e^{r^2/2}}{r^2}.
$$
For the final strict constant, $\sqrt\pi>5/3$, $e>8/3$, and $(9/8)^{3/2}<5/4$ suffice.

Let $s>u$ be the unique solution
$$
\frac{e^{s^2/2}}{s^2}=\frac1{10q}.
$$
This solution satisfies $u<s<2u$. Indeed $r\mapsto e^{r^2/2}/r^2$ is strictly increasing above $\sqrt2$, and the two Mills inequalities give
$$
10q\frac{e^{u^2/2}}{u^2}<\frac{20}{\sqrt{2\pi}u^3}<1,
\qquad
10q\frac{e^{2u^2}}{4u^2}
>\frac{5e^{3u^2/2}}{\sqrt{2\pi}u(u^2+1)}>1.
$$
The latter comparison already follows from $\sqrt{2\pi}<3$ and $e^{u^2}>u^6/6$ at $u=104$.

For $u\leq x\leq s$, the Gaussian hazard bound $\phi(z)/Q(z)<z+z^{-1}$ yields
$$
\frac{Q(x-\delta)}{Q(x)}
<\exp\{\delta(2u+1/2)\}<2.
$$
Also, the lower Mills inequality and the defining equation for $s$ imply
$$
Q(s)>\frac{10q}{\sqrt{2\pi}\,s(s^2+1)},
\qquad
\frac{q\varepsilon}{Q(s)}
<\frac{\sqrt{2\pi}}{10}\varepsilon s(s^2+1)
<3u^5e^{-u^2}<1.
$$
For example the last strict comparison follows from $e^{u^2}>u^{12}/720$ and $u^7>2160$.

At $r\leq u$ a finite cutoff cannot reject a positive null mass. Suppose $u<r\leq s$ and a finite contact has positive null FDP. Necessarily $u\leq x_r<r$, so $x_r-\delta>2$. Apply the preceding cap and shift bounds at $t=x_r-\delta$ to obtain
$$
\frac{F_r(x_r)}{Q(x_r)}
<10\frac{e^{r^2/2}}{r^2}+\frac{\varepsilon}{Q(s)}
<\frac1q+\frac1q=\frac2q,
$$
contradicting the contact identity. Thus positive null FDP requires $R>s$.

The dimension-four coordinate density is symmetric and nonincreasing in absolute value, so $\mathbb P(|rv_1+\mu|\geq x)$ is nondecreasing in $\mu\geq0$. To check this directly, the derivative of the central interval probability is $f_r(x+\mu)-f_r(x-\mu)\leq0$. Consequently $F_r(x)\geq2H_r(x)$ and $\operatorname{FDP}_{\rm pop}\leq\pi_0$ at every contact. The exact $\chi_4$ tail now gives
$$
\operatorname{FDR}_{\rm pop}
\leq\pi_0\mathbb P(R>s)
=\pi_0e^{-s^2/2}(1+s^2/2)
=10q\pi_0(s^{-2}+1/2)
<6q\pi_0.
$$
Finally $M_4=1/\pi$, $\log312>5$, and $\pi<4$, so the proposed coefficient $2+4M_4(1+u^{-2})\log(3u)$ exceeds $7$. The candidate therefore satisfies the claimed bound strictly.

This law is outside both displayed microscopic-mean exclusions on the board: it has unbounded support, and at $b=e^{-2u^2}$ its tail mass is $W((b,\infty))=1/[2(1+e^{-u^2})]>1/4$, whereas $Q(2u)/q<1/4$ by the Mills inequalities.

## Failure

NOT fails first: the infinite-mean Lomax mixture has $\operatorname{FDR}_{\rm pop}<6q\pi_0$, strictly below the proposed right side.
