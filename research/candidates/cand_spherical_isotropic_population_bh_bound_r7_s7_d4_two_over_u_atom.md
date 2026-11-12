---
type: candidate
title: Four-dimensional two-over-u positive atom
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
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:40:00.656Z'
extension_version: 0.0.4
---

## Object

Set $u=104$, $q=2Q(u)$, $d=4$, and $m=2/u$. Take
$$
W=\tfrac12\delta_0+\tfrac12\delta_m,
\qquad \pi_0=\tfrac12.
$$
For every mean use independent uniform directions on $\mathbb S^3$, with zero residual variance and $Z\sim N(0,I_4)$. Use exactly the smallest finite contact $x_r$ from the target definition, with FDP zero when no contact exists. The positive mean is of order $u^{-1}$, outside the previously excluded $[0,u^{-2}]$ support condition.

## Checks

### H1

The tests are $T_{\mu,v}=\mu+v^\top Z$ under $W\otimes\sigma_3$. There is no additional residual noise, as required for the isotropic spherical directional population with zero residual variance.

### H2

The dimension $d=4$ is an integer at least four.

### H3

The two-atom law $W$ is a Borel probability measure on $[0,\infty)$, and its atom at zero has mass $\pi_0=1/2$.

### H4

The directional kernel is $\sigma_3$ at both means and is independent of the mean.

### H5

The object uses the prescribed smallest finite $x\geq u$ with $F_r(x)\geq2Q(x)/q$, and FDP zero in its absence. No different contact or BH threshold is selected.

### H6

Gaussian survival is strictly between zero and $1/2$ at $u=104$, so $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### NOT

The conclusion is not violated: a finite cap estimate gives the stronger bound $\operatorname{FDR}_{\rm pop}<5q\pi_0$.

Put
$$
s=\sqrt{u^2+6\log u},\qquad b=s-m.
$$
Here $b>u$, since $\log104>4$ and $6\log u>4+4/u^2$. For $d=4$ the density of $rv_1$ is
$$
f_r(t)=\frac2{\pi r}\sqrt{1-t^2/r^2}\,\mathbf1_{\{|t|<r\}}.
$$
Consequently, for $0\leq t\leq r$,
$$
H_r(t)\leq A\left(\frac{r-t}{r}\right)^{3/2},
\qquad A=\frac{4\sqrt2}{3\pi}.
$$
This follows by bounding $\sqrt{1-z^2/r^2}\leq\sqrt{2(r-z)/r}$ in the tail integral.

Fix $u<r\leq b$. If $x>r+m$ there are no rejections at cutoff $x$. Otherwise $u\leq x\leq r+m$, and, writing $y=r+m-x\geq0$, monotonicity of $H_r$ gives
$$
F_r(x)\leq2H_r(x-m)\leq2A r^{-3/2}y^{3/2}.
$$
The elementary Mills bounds yield
$$
\frac{Q(u)}{Q(x)}
\leq\frac{x+x^{-1}}u\exp\{(x^2-u^2)/2\}.
$$
Moreover, since $x\geq u$,
$$
\exp\{(x^2-u^2)/2\}
\leq\exp\{((r+m)^2-u^2)/2\}e^{-uy},
\qquad
y^{3/2}e^{-uy}\leq\left(\frac3{2eu}\right)^{3/2}.
$$
Using $r\geq u$, $r+m\leq s$, and $e^{(s^2-u^2)/2}=u^3$, we obtain
$$
\frac{F_r(x)Q(u)}{Q(x)}
\leq2A\left(\frac3{2e}\right)^{3/2}
\left(\frac su+u^{-2}\right)
=\frac{4\sqrt3}{\pi e^{3/2}}\left(\frac su+u^{-2}\right)<1.
$$
For an explicit last comparison, $\log104<5$ implies $s/u<501/500$, and $u^{-2}<1/10000$, so the parenthesis is less than $1003/1000$. The prefactor is less than $7/12$, using $\sqrt3<7/4$, $\pi>3$, and $e^{3/2}>4$. Its product is less than one. Since $q=2Q(u)$, no finite contact exists for $u<r\leq b$.

The symmetric unimodal density $f_r$ implies
$$
H_r(x-\mu)+H_r(x+\mu)\geq2H_r(x)\qquad(\mu,x\geq0).
$$
Indeed its derivative in $\mu$ is $f_r(x-\mu)-f_r(x+\mu)\geq0$, with the density extended by zero outside its support. Thus $F_r(x)\geq2H_r(x)$, and the conditional FDP is at most $\pi_0$. At $r\leq u$ its null numerator is zero. The preceding no-contact interval therefore gives
$$
\operatorname{FDR}_{\rm pop}\leq\pi_0\mathbb P(R>b).
$$
For $R\sim\chi_4$, its exact tail and the lower Mills bound give
$$
\begin{aligned}
\frac{\mathbb P(R>b)}q
&=\frac{(1+b^2/2)e^{-b^2/2}}{2Q(u)}\\
&\leq\frac{\sqrt{2\pi}}2(1+u^{-2})
\left(u^{-2}+\frac{b^2}{2u^2}\right)
\exp\left(\frac{2s}{u}-\frac2{u^2}\right)\\
&<\frac{63}{50}\frac{10001}{10000}\frac{627}{1250}\frac{15}{2}<5.
\end{aligned}
$$
Here $b^2/u^2<s^2/u^2<1003/1000$, $\sqrt{2\pi}/2<63/50$, and $e^{2s/u-2/u^2}<e^{501/250}<15/2$. The exponential bound follows, for example, from $e<68/25$ and $e^{1/250}\leq250/249$.

Finally $M_4=1/\pi$ and $\log312>5$, so the proposed coefficient satisfies
$$
2+4M_4(1+u^{-2})\log(3u)>7>5.
$$
The positive additive term $e^{-2u^2}$ only increases the proposed upper bound. Hence NOT fails.

## Failure

NOT fails first: a cap estimate excludes every finite contact up to radius $b=\sqrt{u^2+6\log u}-2/u$, and the exact $\chi_4$ tail then gives $\operatorname{FDR}_{\rm pop}<5q\pi_0$, strictly below the proposed bound.
