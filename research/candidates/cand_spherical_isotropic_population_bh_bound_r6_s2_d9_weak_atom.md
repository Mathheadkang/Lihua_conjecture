---
type: candidate
title: Dimension-nine weak atom at the smallest allowed Gaussian cutoff
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
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:07:00.541Z'
extension_version: 0.0.4
---

## Object

Take $d=9$, zero residual variance, $u=104$, $q=2Q(104)$, and
$$
W=\tfrac14\delta_0+\tfrac34\delta_{1/104}.
$$
Use the product population $W\otimes\sigma_8$, the shared Gaussian factor $Z\sim N(0,I_9)$, and exactly the finite-contact and no-contact conventions in the target. Thus $\pi_0=1/4$. This tests a small fixed dimension with a positive mean below the support boundaries displayed on the board.

## Checks

### H1

The population is the specified isotropic spherical directional population with zero residual variance: $T_{\mu,v}=\mu+v^\top Z$ has no further noise.

### H2

The dimension $d=9$ is an integer and satisfies $d\geq4$.

### H3

$W$ is a Borel probability measure on $[0,\infty)$ because its two nonnegative atom weights sum to one.

### H4

Directions have the uniform kernel $\sigma_8$ at each of the two means and are independent of the mean. The zero-mean mass is exactly $\pi_0=W(\{0\})=1/4$.

### H5

$q=2Q(104)$ lies in $(0,1)$ and its inverse-tail parameter is $Q^{-1}(q/2)=104$, the allowed endpoint.

### H6

For each $r>0$, use the smallest finite $x\geq u$ satisfying $F_r(x)\geq2Q(x)/q$, with the contact identity from the supplied definition. Set FDP to zero when no finite contact exists. These are exactly the prescribed conventions.

### NOT

NOT fails by the following analytic upper bound. In fact the bound below is independent of the alternative law and the positive null mass, so it excludes every permitted $W$ at $d=9,u=104$; the chosen weak atom is one explicit member.

First, $\operatorname{FDP}_{\mathrm{pop}}(r)\leq\pi_0$. Indeed, the density of $rv_1$ is symmetric and nonincreasing in its absolute argument. For $x\geq0$ the shifted two-sided tail
$$
A(\mu)=H_r(x-\mu)+H_r(x+\mu)
$$
is nondecreasing for $\mu\geq0$: its derivative is $f_r(x-\mu)-f_r(x+\mu)\geq0$, since $|x-\mu|\leq x+\mu$. Consequently $F_r(x)\geq2H_r(x)$, and the finite-contact mass ratio is at most $\pi_0$. Also FDP vanishes for $r\leq u$, and a finite contact $x\geq r$ has zero null mass.

For $r>x\geq u$, the exact dimension-nine cap formula is
$$
H_r(x)=\frac{35}{32}\int_{x/r}^1(1-t^2)^3\,dt.
$$
Put $y=(r^2-x^2)/2$. With $s=r^2(1-t^2)/2$ and $t\geq x/r$, the substitution gives
$$
H_r(x)\leq\frac{35}{16}\frac{y^4}{xr^7}.
$$
The Mills lower bound $Q(x)\geq\varphi(x)x/(1+x^2)$ and $y^4e^{-y}\leq4^4e^{-4}$ therefore imply, simultaneously for every such $x$,
$$
\frac{H_r(x)}{Q(x)}
\leq560\sqrt{2\pi}\,e^{-4}(1+u^{-2})r^{-7}e^{r^2/2}.
$$
Thus no tracking or differentiation of first contacts is needed for this particular fixed-dimension envelope. The $\chi_9$ radial density is
$$
f_R(r)=\frac{\sqrt{2/\pi}}{105}r^8e^{-r^2/2}.
$$
Take $b=\sqrt{u^2+72}$. Integrate the displayed common envelope on $(u,b]$, and use $\operatorname{FDP}\leq\pi_0$ on $(b,\infty)$, to obtain
$$
\frac{\operatorname{FDR}_{\mathrm{pop}}}{q\pi_0}
\leq \frac{32}{3}e^{-4}(1+u^{-2})\frac{b^2-u^2}{2}
+\frac{\mathbb P(R>b)}q.
$$
Here $104<b<105$. The exact odd-dimensional radial tail is
$$
\mathbb P(R>b)=2Q(b)+\sqrt{2/\pi}\,e^{-b^2/2}
\left(b+\frac{b^3}{3}+\frac{b^5}{15}+\frac{b^7}{105}\right).
$$
Apply $2Q(b)\leq\sqrt{2/\pi}e^{-b^2/2}/b$ and $q\geq\sqrt{2/\pi}e^{-u^2/2}u/(u^2+1)$. Since $(u^2+1)/u<105$, this proves
$$
\frac{\mathbb P(R>b)}q
<e^{-36}\,105\left(1+105+\frac{105^3}{3}+\frac{105^5}{15}+\frac{105^7}{105}\right)
=140799422503005\,e^{-36}<\frac1{16}.
$$
For a rational certificate, $e^4>\sum_{j=0}^{12}4^j/j!=25532659/467775>54$, and
$16(140799422503005)<54^9=3904305912313344$.
The same $e^4>54$, together with $1+u^{-2}<10001/10000$, yields
$$
\frac{\operatorname{FDR}_{\mathrm{pop}}}{q\pi_0}
<\frac{64}{9}\frac{10001}{10000}+\frac1{16}
=\frac{645689}{90000}<\frac{15}{2}.
$$
On the other hand,
$$
M_9=\frac{945}{1372\sqrt7}>\frac14,
\qquad \log312>\frac{11}{2},
$$
so the proposed multiplicative coefficient is greater than $2+4(1/4)(11/2)=15/2$. For the first inequality one may square $3780>1372\sqrt7$, obtaining $14288400>13176688$. For the logarithmic inequality, $e<11/4$ and $(11/4)^{11}<312^2$ suffice; $e<11/4$ follows by bounding its series tail after degree two by $2/9$. Thus the FDR is strictly smaller than the proposed multiplicative term alone. The positive additive term $e^{-2u^2}$ only increases the proposed upper bound.

This is a fixed-$d$, fixed-$u$ exclusion; it does not give a uniform bound over dimensions or Gaussian cutoffs.

## Failure

NOT fails first: the dimension-nine radial envelope gives $\operatorname{FDR}_{\mathrm{pop}}/(q\pi_0)<645689/90000<15/2$, below the proposed coefficient.
