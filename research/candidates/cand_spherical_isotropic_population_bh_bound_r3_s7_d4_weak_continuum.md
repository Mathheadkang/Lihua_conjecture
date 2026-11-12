---
type: candidate
title: Four-dimensional weak continuous alternatives
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
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $a=1/u$, and
$$
W=\tfrac12\delta_0+\tfrac12\operatorname{Unif}[0,a].
$$
Use the product population $W(d\mu)\sigma_3(dv)$, $Z\sim N(0,I_4)$, and $T_{\mu,v}=\mu+v^\top Z$ with no residual noise. Use exactly the specified smallest finite admissible cutoff $x_r$ and zero FDP when there is none. Thus $\pi_0=1/2$.

## Checks

### H1

$d=4$ is an integer at least four.

### H2

$W$ is a Borel probability law on $[0,\infty)$. Its uniform component has no atom at zero, so $W(\{0\})=1/2$. Every absolute mean belongs to $[0,1/u]$.

### H3

At every absolute mean the conditional directional kernel is exactly $\sigma_3$, independent of that mean.

### H4

The sole sampling randomness is $Z\sim N(0,I_4)$, and $T_{\mu,v}=\mu+v^\top Z$ has zero residual variance.

### H5

$q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

The cutoff and FDP are the target's population definitions, including the smallest finite cutoff and the no-contact convention. No alternative branch of a contact is selected.

### NOT

**Fail.** The following analytic radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, strictly less than the claimed right side.

Put $k=3/2$, $p=1/2$, $c=2/\pi$, $K=4$, and
$$
r_*^2=u^2+2(d-1)\log u-2\log K,\qquad b=r_*+a.
$$
For $0\le t\le r$, the spherical density gives
$$
H_r(t)=c\int_{t/r}^1(1-v^2)^p\,dv
\le\frac{c2^p}{k}\left(\frac{r-t}{r}\right)^k.
$$
Because every mean is at most $a$, $F_r(x)\le2H_r(x-a)$. If $r\le r_*$ and $x\ge u$ can have positive rejection mass, then $u\le x\le b$ and $r\ge u-a$. Write $s=b-x\ge0$. The Mills inequalities give
$$
\frac{Q(u)}{Q(x)}\le\frac{x^2+1}{ux}\exp\{(x^2-u^2)/2\}.
$$
Use $r+a-x\le s$, $b^2-x^2\ge2us$, and
$\sup_{s\ge0}s^ke^{-us}=(k/(eu))^k$. It follows that
$$
\frac{F_r(x)Q(u)}{Q(x)}
\le\frac{L}{K}\left(\frac ur\right)^k
\frac{x^2+1}{ux}\exp\{r_*/u+1/(2u^2)\},
\qquad
L=\frac{2c2^p}{k}\left(\frac ke\right)^k.
$$
Here $r_*^2<u^2+50$, $r_*/u<101/100$, and $b/u<102/100$. Therefore the three factors following $L/K$ are respectively less than $11/10$, $11/10$, and $3$, with product less than $4$. For the first bound use $r\ge u-a$ and $k<3$; for the last use $r_*/u+1/(2u^2)<21/20$ and $e^{21/20}<3$. Also $\pi>3$, $\sqrt2<3/2$, and $e>8/3$ imply
$$
L<\frac43\left(\frac9{16}\right)^{3/2}=\frac9{16}<1.
$$
Consequently $F_r(x)Q(u)/Q(x)<4L/K<1$ for every possible $x\ge u$ when $r\le r_*$. For $x>b$, $F_r(x)=0$ directly. The BH admissibility condition is $F_r(x)Q(u)/Q(x)\ge1$, so no finite contact exists on $r\le r_*$.

Since every FDP is at most one, $\operatorname{FDR}_{\rm pop}\le\mathbb P(R>r_*)$. Write $z=r_*^2/2$. The exact $\chi_4$ tail and the lower Mills bound yield
$$
\frac{\mathbb P(R>r_*)}{q}
\le4\sqrt{\frac\pi2}\frac{u^2+1}{u^4}(1+z)
<4\frac{63}{50}\frac{1001}{1000}\frac{51}{100}<3.
$$
The last bounds use $r_*^2<(101/100)u^2$, $1+z<(51/100)u^2$, and $u^2+1<(1001/1000)u^2$; these hold at $u=104$.

Finally $M_4=1/\pi>1/4$ and $\log(3u)>4$. Since $\pi_0=1/2$, the proposed right side is strictly larger than
$$
\frac q2\{2+4(1/4)4\}=3q.
$$
Thus the proposed bound holds for this object. This is an analytic failed counterexample, not a numerical infeasibility conclusion.

## Failure

NOT fails first: a no-contact radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, while the claimed right side exceeds $3q$.
