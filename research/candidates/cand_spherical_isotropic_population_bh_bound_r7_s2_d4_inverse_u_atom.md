---
type: candidate
title: Dimension four with an inverse-u positive mean
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
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:40:00.656Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $m=1/u$, and
$$
W=\tfrac12\delta_0+\tfrac12\delta_m,\qquad \pi_0=\tfrac12.
$$
At each mean use the uniform law on $\mathbb S^3$, independently of the mean, and use zero residual variance. Let $Z\sim N(0,I_4)$ and $R=\|Z\|_2$. Use exactly the smallest finite Gaussian-statistic contact from the target, with FDP zero when there is no finite contact.

The positive mean $u^{-1}$ exceeds the board's microscopic support endpoint $u^{-2}$. The following certificate uses a cap bound and a radial exclusion and does not require finding or differentiating the first contact.

## Checks

### H1

Pass: $d=4$ is an integer at least four.

### H2

Pass: $W$ is a Borel probability measure on $[0,\infty)$ and its atom at zero has mass $\pi_0=1/2$.

### H3

Pass: the joint population measure is $W\otimes\sigma_3$. Thus the directional kernel is uniform at both absolute means and independent of the mean.

### H4

Pass: the only sampling randomness is $Z\sim N(0,I_4)$, with statistic $T_{\mu,v}=\mu+v^\top Z$ and no residual noise.

### H5

Pass: $q=2Q(104)\in(0,1)$, so $Q^{-1}(q/2)=104\geq104$.

### H6

Pass: use $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when this set is nonempty. Otherwise the FDP is zero. At finite contact use the stipulated identity $F_r(x_r)=2Q(x_r)/q$ and FDP $q\pi_0H_r(x_r)/Q(x_r)$.

### NOT

Fail: in fact
$$
\operatorname{FDR}_{\mathrm{pop}}<(3+4u^{-2})q\pi_0<4q\pi_0,
$$
which is below the proposed right side. Here is an explicit certificate.

For $d=4$ the directional density on $(-r,r)$ is
$$
f_r(t)=\frac{2}{\pi r^2}\sqrt{r^2-t^2}.
$$
For $2\leq t<r$, changing variables in its upper-tail integral gives
$$
H_r(t)\leq\frac{2}{\pi r^2t}\int_t^r s\sqrt{r^2-s^2}\,ds
=\frac{2(r^2-t^2)^{3/2}}{3\pi r^2t}.
$$
The lower Mills inequality $Q(t)\geq\phi(t)t/(t^2+1)$ and the maximum of $y^{3/2}e^{-y/2}$ at $y=3$ therefore imply
$$
\frac{H_r(t)}{Q(t)}
\leq \frac{e^{r^2/2}}{r^2}
\frac{2\sqrt{2\pi}}{3\pi}\frac54
\left(\frac3e\right)^{3/2}
<\frac{e^{r^2/2}}{r^2}.
$$
For completeness, the square of the constant is $75/(2\pi e^3)<1$, using $\pi>3$ and $e>5/2$.

Put $b=11u/10$. A positive FDP requires $r>x_r\geq u$. If $r\leq b$ and a finite contact has positive FDP, then $x=x_r<r+m$, because all population statistics have absolute value at most $r+m$. Set $t=x-m$; then $2<t<r$. Monotonicity of $H_r$ gives
$$
F_r(x)=H_r(x)+\tfrac12H_r(x-m)+\tfrac12H_r(x+m)
\leq2H_r(x-m).
$$
Upper and lower Mills inequalities also give
$$
\frac{Q(x-m)}{Q(x)}
\leq \frac{x^2+1}{x(x-m)}e^{mx-m^2/2}
\leq\frac{1+u^{-2}}{1-u^{-2}}
e^{11/10+1/(2u^2)}<4.
$$
The last strict inequality follows from $(1+u^{-2})/(1-u^{-2})<101/100$, $11/10+1/(2u^2)<6/5$, and
$e^{6/5}=e\,e^{1/5}<(11/4)(5/4)=55/16$.
Consequently at this contact
$$
\frac2q=\frac{F_r(x)}{Q(x)}
<8\frac{e^{r^2/2}}{r^2}.
$$
The function $g(r)=e^{r^2/2}/r^2$ is strictly increasing for $r>\sqrt2$. Also $qg(u)<2/(\sqrt{2\pi}u^3)<1/4$ by the upper Mills inequality. There is therefore a unique $s>u$ with
$$
g(s)=\frac1{4q},
$$
and any positive FDP with $r\leq b$ requires $r>s$.

The exact $\chi_4$ survival function gives
$$
\mathbb P(R>s)=(1+s^2/2)e^{-s^2/2}
=4q(1/s^2+1/2)<q(2+4/u^2).
$$
Moreover $\mathbb P(R>b)<q$. To verify the latter without a numerical tail evaluation, write $z=u^2\geq10000$. The lower Mills inequality and $\sqrt{2\pi}<3$ give
$$
\frac{\mathbb P(R>b)}q
\leq(1+121z/200)\frac{\sqrt{2\pi}(z+1)}{2\sqrt z}
e^{-21z/200}
<6z^{3/2}e^{-z/10}
<\frac{36000}{z^{3/2}}<1,
$$
where $e^{z/10}>(z/10)^3/6$ supplies the penultimate inequality.

Finally, the symmetric unimodal density $f_r$ assigns maximal mass to a centered interval of any fixed length. Thus shifting a mean cannot decrease the two-sided rejection mass, so $F_r(x)\geq2H_r(x)$ and the stipulated FDP is at most $\pi_0$. Combining this with the necessary radial events yields
$$
\operatorname{FDR}_{\mathrm{pop}}
\leq\pi_0\{\mathbb P(R>s)+\mathbb P(R>b)\}
<(3+4/u^2)q\pi_0<4q\pi_0.
$$
Since $M_4=1/\pi$, $\log312>5$, and $\pi<4$, the proposed coefficient $2+4M_4(1+u^{-2})\log(3u)$ is greater than seven. Hence the proposed conclusion holds strictly for this object.

## Failure

NOT fails first: the inverse-u mean forces positive null FDP into radial events whose exact tails give FDR below $4q\pi_0$, whereas the proposed coefficient exceeds seven.
