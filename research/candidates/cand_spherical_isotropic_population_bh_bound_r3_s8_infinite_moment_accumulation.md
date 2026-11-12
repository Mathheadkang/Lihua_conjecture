---
type: candidate
title: Infinite-moment mean law with alternative atoms accumulating at the null
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
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=5$, $u=104$, $q=2Q(u)$, $\eta=u^{-8}$, and
$$
W=\frac12\delta_0+
\left(\frac12-\eta\right)\sum_{k=1}^{\infty}2^{-k}\delta_{1/(ku)}
+\eta\sum_{k=1}^{\infty}2^{-k}\delta_{4^ku}.
$$
Use population measure $W\otimes\sigma_4$, sampling variable $Z\sim N(0,I_5)$, statistics $T_{\mu,v}=\mu+v^\top Z$, and exactly the smallest finite admissible Gaussian cutoff from the target definition. The alternative atoms accumulate at zero, while the unbounded part has infinite first moment. Thus this object tests the absence of moment assumptions and the possible presence of arbitrarily weak alternatives simultaneously; it is outside the recorded alternative-support restriction $[4u,\infty)$.

## Checks

### H1

The dimension $d=5$ is an integer at least four.

### H2

Every atom is nonnegative, $0<\eta<1/2$, and $\sum_{k\ge1}2^{-k}=1$. Hence $W$ is a Borel probability law on $[0,\infty)$, with $\pi_0=W(\{0\})=1/2$. It has unbounded support and
$$
\int\mu\,W(d\mu)\geq\eta u\sum_{k=1}^{\infty}2^k=\infty,
$$
which the hypothesis permits.

### H3

The population measure is the product $W\otimes\sigma_4$; in particular its specified directional kernel is uniform and independent of the mean at every mean, including zero and all accumulation points.

### H4

The only sampling randomness is $Z\sim N(0,I_5)$ and $T_{\mu,v}=\mu+v^\top Z$, so residual variance is zero.

### H5

The choice $q=2Q(104)$ lies in $(0,1)$ and satisfies $Q^{-1}(q/2)=104$ exactly.

### H6

Use $x_r=\min\{x\geq u:F_r(x)\geq Q(x)/Q(u)\}$ when this set is nonempty, and the stated zero-FDP convention otherwise. This is precisely the target's largest population BH threshold, with the same contact identity and FDP.

### NOT

The proposed conclusion does not fail. The following exact envelope bounds the entire FDR, without inferring absence of contacts from floating-point calculations.

Define
$$
r_0=\sqrt{u^2+8\log u-4},\qquad m=u^{-1},\qquad A(r)=(r^2-u^2)/2.
$$
For $d=5$ and $0\leq t\leq r$, the spherical tail has the exact expression
$$
H_r(t)=\frac{(1-t/r)^2(2+t/r)}4
\leq\frac{3(r-t)^2}{4r^2}.
$$
For $t\geq r$ it is zero. Fix $u\leq r\leq r_0$, $u\leq x\leq r$, and write $y=r-x\geq0$. All except $\eta$ of the mean mass is in $[0,m]$. Because $x-m>0$, its two spherical tails are bounded by $3\{(y+m)^2+y^2\}/(4r^2)\leq3(y+m)^2/(2r^2)$. The remaining mass contributes at most $\eta$. Thus
$$
F_r(x)\leq\frac{3(y+m)^2}{2r^2}+\eta.
$$
The usual Gaussian Mills inequalities, $\phi(t)t/(t^2+1)<Q(t)<\phi(t)/t$ for $t>0$, give
$$
\frac{Q(x)}{Q(u)}\geq
\frac{u^2}{r^2+1}e^{-A(r)}e^{uy},
$$
using $(r^2-x^2)/2\geq uy$. Since
$$
\sup_{y\geq0}(y+u^{-1})^2e^{-uy}=4e^{-1}u^{-2},
$$
the admissibility ratio throughout this range is bounded by
$$
\frac{F_r(x)}{Q(x)/Q(u)}
\leq 6(1+u^{-2})e^{-3}
+\eta\frac{r_0^2+1}{u^2}e^{A(r_0)}
=6(1+u^{-2})e^{-3}+
\frac{r_0^2+1}{u^6}e^{-2}<1.
$$
The last inequality follows directly from $u=104$, $e^3>16$, and $r_0^2+1<2u^2$. There is consequently no admissible cutoff in $[u,r]$ for $r\leq r_0$. For $r<u$ every permitted cutoff already exceeds the null support; for $u\leq r\leq r_0$ every finite first contact must likewise exceed $r$. In either case the null rejection mass is zero. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}\leq\mathbb P(R>r_0).
$$
For $R\sim\chi_5$, integration by parts gives the exact identity
$$
\mathbb P(R>r)=\frac{\sqrt{2/\pi}}3(r^3+3r)e^{-r^2/2}+2Q(r).
$$
Applying the same Mills inequalities and $e^{-A(r_0)}=e^2/u^4$ yields
$$
\frac{\mathbb P(R>r_0)}q
\leq\frac{e^2}{3}(1+u^{-2})
\left\{(r_0/u)^3+\frac{3(r_0/u)}{u^2}\right\}
+(1+u^{-2})\frac{e^2}{u^4}<3.
$$
For an explicit rational comparison, $\log104<5$ implies $r_0/u<101/100$; hence the braces are below $11/10$, while $1+u^{-2}<101/100$, $e^2<8$, and the last summand is below $1/1000$. The resulting upper bound is $8888/3000+1/1000<3$.

Here $M_5=1/(2\sqrt3)$, so the target's right side divided by $q$ is
$$
1+\frac{1+u^{-2}}{\sqrt3}\log(3u)+\frac{e^{-2u^2}}q>4.
$$
Indeed, $e^2<8$ implies $\log2>2/3$, so $\log312>\log256>16/3>3\sqrt3$. Thus the FDR is strictly below the proposed right side.

For reproducibility only, an ordinary floating diagnostic gives $r_0\approx104.1592776817943$, contact-ratio upper envelope about $0.29875003$, tail-ratio upper envelope about $2.47526560$, and claimed $q$ coefficient about $4.31603099$. These decimals are not used to certify the failed NOT check; the displayed inequalities do so.

## Failure

NOT is the first failed check: despite unbounded support, infinite first moment, and alternative atoms accumulating at zero, the exact global envelope gives $\operatorname{FDR}_{\mathrm{pop}}<3q$ while the proposed right side exceeds $4q$.
