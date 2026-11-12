---
type: candidate
title: Logarithmically accumulating weak alternatives at the null boundary
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
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $a=1/u$, and
$$
W=\tfrac12\delta_0+\tfrac12\nu,
\qquad
\nu(d\mu)=\frac{\mathbf 1_{(0,a]}(\mu)}{\mu\{1+\log(a/\mu)\}^2}\,d\mu.
$$
Use the product law $W(d\mu)\sigma_3(dv)$ and the statistic $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_4)$, with the prescribed smallest finite admissible Gaussian-statistic cutoff. This law places alternative mass arbitrarily close to zero: for $0<b\le a$,
$$
\nu((0,b])=\frac1{1+\log(a/b)}.
$$
In particular there is no positive lower bound on the alternative means, despite $\pi_0=1/2$.

## Checks

### H1

Pass. There is zero residual variance: the statistic is exactly $\mu+v^\top Z$, without additional noise.

### H2

Pass. The dimension is the allowed integer $d=4$.

### H3

Pass. The density defining $\nu$ is Borel and nonnegative, and the substitution $s=\log(a/\mu)$ gives
$$
\nu((0,a])=\int_0^\infty(1+s)^{-2}\,ds=1.
$$
It gives zero mass to $\{0\}$, so $W$ is a Borel probability law on $[0,\infty)$ with $\pi_0=W(\{0\})=1/2$. Its support is contained in $[0,a]$.

### H4

Pass. Directions have the uniform law $\sigma_3$ conditional on every mean, independently of that mean, by the stipulated product population law.

### H5

Pass. $q=2Q(104)$ belongs to $(0,1)$ and satisfies $Q^{-1}(q/2)=104$ exactly. No floating-point representation of this very small level is used.

### H6

Pass. At radius $r$, form the specified $F_r$, choose the smallest finite $x\ge u$ satisfying $F_r(x)\ge Q(x)/Q(u)$, and set the FDP to zero if this set is empty. The FDR is its expectation over the $\chi_4$ radius. Thus the procedure and the no-contact convention are exactly those in the target.

### NOT

Fail. An exact upper bound gives $\operatorname{FDR}_{\rm pop}<2q=4q\pi_0$, strictly below the proposed right side. The following calculation also applies to any mean law supported in $[0,1/u]$ at these $d,u$.

Write
$$
L=\log u,\qquad r_0=u+\frac{3L-1}{u}.
$$
First there is no admissible cutoff when $r\le r_0$. Because every mean is at most $a$, monotonicity of the spherical tail gives
$$
F_r(x)\le2H_r(x-a).
$$
For $r\le u-a$ this is zero at every $x\ge u$. Otherwise a positive value requires $u\le x<r+a$, and in dimension four
$$
H_r(x-a)=\frac2\pi\int_{(x-a)/r}^1\sqrt{1-z^2}\,dz
\le\frac{4\sqrt2}{3\pi}\left(\frac{r+a-x}{r}\right)^{3/2}.
$$
The usual integral bounds $Q(u)<\phi(u)/u$ and $Q(x)>\phi(x)x/(1+x^2)$ imply
$$
\frac{F_r(x)Q(u)}{Q(x)}
<\frac{8\sqrt2}{3\pi}\frac{(r+a-x)^{3/2}}{r^{3/2}}
\frac{x+1/x}{u}\exp\{(x^2-u^2)/2\}.
$$
For $r\le r_0$, put $t=r+a-x\ge0$. Then $r\ge u-a$, $x+1/x\le r_0+a+1/u$, and
$$
\frac{x^2-u^2}{2}\le\frac{(r_0+a)^2-u^2}{2}-ut.
$$
Using $\sup_{t\ge0}t^{3/2}e^{-ut}=(3/(2eu))^{3/2}$ and $r_0+a=u+3L/u$, the displayed ratio is bounded by
$$
C=\frac{8\sqrt2}{3\pi}\left(\frac3{2e}\right)^{3/2}
(1-u^{-2})^{-3/2}
\left(1+\frac{3L+1}{u^2}\right)
\exp\left(\frac{9L^2}{2u^2}\right)<1.
$$
The last inequality needs no numerical quadrature. Indeed $u>100$, $L<5$, $\pi>3$, $\sqrt2<3/2$, and $e>5/2$ give
$$
C<\frac45\cdot\frac{1001}{1000}\cdot\frac{1002}{1000}\cdot\frac{1012}{1000}<1.
$$
Here the three factors respectively bound $(1-u^{-2})^{-3/2}$, $1+(3L+1)/u^2$, and the exponential; for the last factor one can use $e^y\le(1-y)^{-1}$ at $y<225/20000$. Consequently $F_r(x)<Q(x)/Q(u)$ for every finite $x\ge u$ when $r\le r_0$.

The FDP lies in $[0,1]$, so the exact $\chi_4$ survival function gives
$$
\operatorname{FDR}_{\rm pop}
\le\mathbb P(R>r_0)
=\left(1+\frac{r_0^2}{2}\right)e^{-r_0^2/2}.
$$
Put $c=3L-1$. We have $0<c<14$, $r_0^2/2<u^2/2+15$, and
$$
\exp\{-(r_0^2-u^2)/2\}=e\,u^{-3}e^{-c^2/(2u^2)}\le e\,u^{-3}.
$$
The lower Mills bound for $Q(u)$ therefore yields
$$
\frac{\mathbb P(R>r_0)}q
<\frac{e\sqrt{2\pi}}2(1+u^{-2})\left(\frac12+16u^{-2}\right)
<\frac{11}{3}\cdot\frac{10001}{10000}\cdot\frac{5016}{10000}<2,
$$
where $e<11/4$ and $\sqrt{2\pi}<8/3$ suffice for the second inequality. Hence $\operatorname{FDR}_{\rm pop}<2q=4q\pi_0$.

Finally $M_4=1/\pi$, and $\log(3u)=\log312>2$ while $\pi<4$. Thus
$$
2+4M_4(1+u^{-2})\log(3u)>4.
$$
The proposed right side is strictly larger than $4q\pi_0$, so this object does not violate the conclusion.

## Failure

NOT is the first failed check: logarithmically accumulating positive means satisfy every hypothesis, but a uniform radial exclusion and the exact $\chi_4$ tail give $\operatorname{FDR}_{\rm pop}<4q\pi_0$.
