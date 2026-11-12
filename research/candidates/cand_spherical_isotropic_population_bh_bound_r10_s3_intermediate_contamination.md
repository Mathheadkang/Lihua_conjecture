---
type: candidate
title: Intermediate exponential contamination just above the mean boundary
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
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T07:46:48.544Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$,
$\varepsilon=e^{-u^2/4}$, and
$$
W=(1-\varepsilon)\delta_0+\varepsilon\delta_{u+u^{-2}}.
$$
Use the product directional population $W\otimes\sigma_3$, the shared factor
$Z\sim N(0,I_4)$, zero residual variance, and the prescribed smallest finite
Gaussian-statistic BH contact. In particular $\pi_0=1-\varepsilon$.
The estimates below hold for every real $u\ge104$ with these choices.

This tests an intermediate contamination size. It is outside the displayed
previous tiny-contamination premise: Mills bounds give
$$
\frac{Q(2u)}q
\le\frac{u^2+1}{4u^2}e^{-3u^2/2}
<e^{-u^2/4}=\varepsilon.
$$
Its alternative mass is also below the displayed one-percent and one-half
mass-floor cases. The new split radius is $6u/5$ rather than $2u$.

## Checks

### H1

Pass. The dimension $d=4$ is an integer at the allowed lower endpoint.

### H2

Pass. The two displayed nonnegative atoms have masses summing to one, so
$W$ is a Borel probability law on $[0,\infty)$.

### H3

Pass. At both means the conditional directional law is exactly $\sigma_3$;
the mean and direction are independent by the product construction.

### H4

Pass. The statistic is exactly $\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and
no residual noise.

### H5

Pass. Since $Q(104)\in(0,1/2)$, the displayed $q$ is in $(0,1)$ and
$Q^{-1}(q/2)=104$.

### H6

Pass. Use $x_r=\min\{x\ge u:F_r(x)\ge2Q(x)/q\}$ when the set is nonempty,
and FDP zero when it is empty, exactly as prescribed.

### NOT

Fail. The population FDR is less than $3q$, below the proposed bound.
Here is a direct bound including all finite contacts, without choosing a
contact branch.

Put $a=6/5$. Mills bounds, valid since $u\ge104$, give
$$
\frac{Q(au)}q
\ge \frac{au^2}{2(1+a^2u^2)}e^{-(a^2-1)u^2/2}
\ge\frac15e^{-11u^2/50}
\ge e^{-u^2/4}=\varepsilon.
$$
The last inequality follows from $e^{3u^2/100}\ge5$.
Write $A_r(x)=H_r(x-u-u^{-2})+H_r(x+u+u^{-2})\le1$.
If FDP is positive at $r\le au$, then a finite contact exists with
$u\le x_r<r\le au$. At that contact,
$$
2\pi_0H_r(x_r)
=\frac{2Q(x_r)}q-\varepsilon A_r(x_r)
\ge\frac{Q(x_r)}q,
$$
because $\varepsilon\le Q(au)/q\le Q(x_r)/q$. Consequently
$H_r(x_r)/Q(x_r)\ge1/(2\pi_0q)\ge1/(2q)$.

For $d=4$ and $u\le x<r$, the exact cap integral implies
$$
H_r(x)=\frac2\pi\int_{x/r}^1\sqrt{1-t^2}\,dt
\le\frac{4\sqrt2}{3\pi}\left(\frac{r-x}{r}\right)^{3/2}.
$$
With $h=r-x$, Mills' lower bound and
$e^{x^2/2}\le e^{r^2/2}e^{-rh/2}$ yield
$$
\frac{H_r(x)}{Q(x)}
\le C(1+u^{-2})\frac{e^{r^2/2}}{r^2},
\qquad C=\frac{8\sqrt3}{\sqrt\pi}e^{-3/2}<2.
$$
Indeed $x+x^{-1}\le r(1+u^{-2})$ and
$\max_{h\ge0}h^{3/2}e^{-rh/2}=(3/r)^{3/2}e^{-3/2}$.
Thus every positive-FDP radius $r\le au$ satisfies
$$
g(r):=r^2e^{-r^2/2}<4(1+u^{-2})q.
$$
The function $g$ strictly decreases on $[u,\infty)$; Mills' upper bound gives
$g(u)/q\ge\sqrt{2\pi}u^3/2>4(1+u^{-2})$. There is therefore a unique
$b>u$ with $g(b)=4(1+u^{-2})q$, and every such radius exceeds $b$.

For $R\sim\chi_4$ the exact tail is
$\Pr(R\ge t)=(1+t^2/2)e^{-t^2/2}$. Hence
$$
\Pr(R\ge b)
=2(1+u^{-2})(1+2/b^2)q
<\frac52q.
$$
The remaining radial tail obeys
$$
\frac{\Pr(R>au)}q
\le\sqrt{\frac\pi2}(u+u^{-1})(1+18u^2/25)e^{-11u^2/50}
<3u^3e^{-11u^2/50}
\le\frac{18}{(11/50)^3u^3}<\frac12.
$$
Here $e^y\ge y^3/6$ supplies the penultimate inequality. Since FDP is at most
one, the two radial regions give
$$
\operatorname{FDR}_{\rm pop}
\le\Pr(R\ge b)+\Pr(R>au)<3q.
$$
Finally $M_4=1/\pi$, $\log(3u)>5$, and $\pi<4$, so the target's bracket is
strictly greater than $7$. Also $\pi_0>1/2$. Its right-hand side is therefore
strictly greater than $(7/2)q>3q$, proving that NOT fails.

## Failure

NOT fails first: this intermediate contamination family lies outside the previously displayed tiny-mass premise but a split at $6u/5$ gives FDR less than $3q$, below the target bound.
